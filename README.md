## Project — Equalization in Fiber-Optic Communication using Neural Networks

The project implements deep learning for a point-to-point optical fiber transmission system. It is divided into two parts: a classical communication chain built from scratch, and a neural equalizer trained to compensate for nonlinear channel distortions.

### Part I: Simplified Point-to-Point Communication System

#### 1.1 Transmitter

- Implemented a **Bernoulli binary source** with i.i.d. bits at probability $p = 1/2$.
- Generated and normalized a square **16-QAM constellation** with unit average symbol energy.

  <img src="PASTE_GITHUB_URL_FOR_fig_q2_constellation" height="220">

- Labeled constellation points using **Gray coding**, ensuring adjacent symbols differ by only one bit.

  <img src="PASTE_GITHUB_URL_FOR_fig_q3_gray_mapping" height="220">

- Implemented a **bit-to-symbol mapper** partitioning the bit stream into groups of $\log_2 M$ bits.
- Constructed the transmitted waveform using both **sinc** and **Root-Raised-Cosine (RRC)** pulse shaping, and plotted the signal in time and frequency domains.

  <img src="PASTE_GITHUB_URL_FOR_fig_q7_sinc" height="250">

#### 1.2 Channel Model

- Derived the units of the physical parameters ($\beta_2$, $\gamma$, $\sigma_0^2$) of the **stochastic Nonlinear Schrödinger (NLS) equation** governing pulse propagation in optical fiber.
- Normalized the NLS equation to a dimensionless form by choosing appropriate scale factors $P_0$, $T_0$, $L_0$.
- Computed all **physical and normalized channel parameters** for a 1000 km fiber link at 10 GHz bandwidth (dispersion $D = 17$ ps/(nm·km), nonlinearity $\gamma = 1.27$ W⁻¹km⁻¹).
- Solved the **linearized fiber channel** in the frequency domain and characterized the additive noise process $\hat{z}(\omega)$ as zero-mean circularly symmetric complex Gaussian, with variance growing linearly with propagation distance.
- Derived the **channel impulse response** $h(t,z) = \frac{e^{j\pi/4}}{\sqrt{4\pi z}} \exp\!\left(-j\frac{t^2}{4z}\right)$ and established the discrete-time channel model via DFT.

#### 1.3 Receiver

- Implemented **frequency-domain equalization** by inverting the dispersive phase response $\hat{h}^{-1}(\omega, L) = e^{-j\omega^2 L}$, and validated on a noiseless Gaussian test signal (residual error $\approx 10^{-15}$).

  <img src="PASTE_GITHUB_URL_FOR_fig_q17_equalization" height="220">

- Demonstrated **inter-symbol interference (ISI)** from dispersion using a two-pulse experiment, confirming that linear equalization perfectly cancels ISI in the noise-free regime.

  <img src="PASTE_GITHUB_URL_FOR_fig_q21_isi" height="250">

- Verified the complete communication chain with zero noise (symbol error = 0) for both sinc and RRC pulse shapes.
- Plotted **BER and SER vs. SNR** for 16-QAM over the implemented fiber channel, for both sinc and RRC pulse shapes, showing the expected monotonic decrease in error rate.

  <img src="PASTE_GITHUB_URL_FOR_fig_q22_ber_ser" height="280">

- Plotted the **transmitter/receiver constellation clouds** at representative SNR, confirming tighter symbol clusters at higher SNR.

  <img src="PASTE_GITHUB_URL_FOR_fig_q22_const_sinc" height="230">

---

### Part II: Neural Equalization

#### Generative Channel Model

- Built a fast **generative channel simulator** based on the full stochastic NLS model at the grading operating point: $M = 16$, $B = 10$ GHz, $L = 1000$ km, SNR $= 35$ dB.
- Implemented precomputed **pulse basis matrices** for efficient modulation and demodulation, reducing repeated computation during dataset generation.

#### Training Data Set & Preprocessing

- Generated a dataset of 400,000 symbols (12,500 examples × 32 symbols/block) of paired received/transmitted soft symbol blocks.
- Preprocessed the data in three steps before training:
  - **Global phase correction**: estimated and removed the common phase rotation.
  - **Normalization**: standardized real and imaginary parts independently using training-set statistics.
  - **Train/validation/test split**: 80% / 10% / 10%.

#### Predictive Equalizers

Two neural receiver architectures were implemented and compared:

- **Dilated Residual CNN equalizer**: a many-to-many convolutional network with dilated convolutions and residual connections. Dilation enlarges the receptive field without increasing parameter count; residual connections improve optimization. (8,542 parameters)
- **BiLSTM-FC equalizer**: a bidirectional LSTM processing the received symbol sequence in both directions, followed by fully connected layers. Exploits temporal dependencies across neighboring symbols. (51,586 parameters)

Both networks were trained with **MSE loss**, Adam optimizer, learning-rate reduction on plateau, gradient clipping, and early stopping on validation loss.

#### Results

**Training curves** for both architectures and pulse shapes:

<div style="display: flex; justify-content: space-between;">
  <img src="PASTE_GITHUB_URL_FOR_fig_nn_sinc_training" height="220">
  <img src="PASTE_GITHUB_URL_FOR_fig_nn_rrc_training" height="220">
</div>

**Constellation clouds** before and after neural equalization (SINC / RRC):

<div style="display: flex; justify-content: space-between;">
  <img src="PASTE_GITHUB_URL_FOR_fig_nn_sinc_constellation" height="220">
  <img src="PASTE_GITHUB_URL_FOR_fig_nn_rrc_constellation" height="220">
</div>

**Final comparison** (at SNR = 35 dB, 16-QAM, $L = 1000$ km):

| Model | BER | SER | MI [bits/sym] | #params |
|---|---|---|---|---|
| SINC – Linear baseline | 4.55 × 10⁻³ | — | 3.7632 | 0 |
| SINC – Dilated CNN | **1.88 × 10⁻⁵** | 7.50 × 10⁻⁵ | **4.0000** | 8,542 |
| SINC – BiLSTM-FC | 2.20 × 10⁻³ | 8.58 × 10⁻³ | 3.9207 | 51,586 |
| RRC – Linear baseline | 4.36 × 10⁻³ | — | 3.7988 | 0 |
| RRC – Dilated CNN | **6.25 × 10⁻⁶** | 2.50 × 10⁻⁵ | **4.0000** | 8,542 |
| RRC – BiLSTM-FC | 1.12 × 10⁻³ | 4.45 × 10⁻³ | 3.9761 | 51,586 |

The dilated CNN achieves the best performance-complexity trade-off, reaching perfect mutual information (4 bits/sym) with far fewer parameters than the BiLSTM model.

---

## Presentation

As part of the course, I read and presented the paper [**Neural Networks for Decoding Error-Correcting Codes in Data Communications**](https://ieeexplore.ieee.org/). The presentation covers how neural networks can be used to learn decoding algorithms over Tanner graphs, replacing or augmenting classical belief propagation. Topics covered:

- **System model & LLRs**: Linear block codes, BPSK over AWGN, channel log-likelihood ratios.
- **Baseline decoding**: Standard Belief Propagation (BP) and Min-Sum algorithm on the Tanner graph.
- **Neural decoders**: Model-agnostic (MLP, CNN, RNN, Autoencoder, Transformer, GNN) and model-based (unrolled BP with trainable weights).
- **Weighted Belief Propagation (WBP) / Weighted Min-Sum (WMS)**: Introduced per-edge learnable weights $\gamma_{v,c}^{(t)}$ and $\beta_{c,v}^{(t)}$ with parameter sharing schemes (Type Ta, TaVC, TbVC).
- **Learned BP**: Tanner graph unrolled into an RNN with iteration-dependent weights trained end-to-end.
- **Adaptive Learned BP**: Weights adapted per received word — parallel WMS decoder running $\nu$ candidates and selecting the best by syndrome weight; two-stage decoder replacing the search with a lightweight CNN predictor.
- **GNN decoder**: Replaced BP message-passing rules with trainable MLP functions on the bipartite Tanner graph, achieving near-BP performance with fewer iterations.

<img src="PASTE_GITHUB_URL_FOR_presentation_slide" height="350">
