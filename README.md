# Deep-Learning

This repository contains the code and documentation for the Neural Networks course homework assignments. Each folder represents a specific paper implementation. Below is a list of projects along with a brief description of their contents.

---

## Home Work 1

Part A: Implemnting and training **Adaline** and **Madaline** networks on **Iris dataset**
<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/user-attachments/assets/85d6e45a-31c2-4008-a5b1-823528f70329" width="300">
  <img src="https://github.com/user-attachments/assets/2ba4384e-2a9d-4407-8258-83f264157ea2" width="300">
</div>

- implemnting deep autoencoder for decreaze of data dimentions
- Knowledge distribution from teacher to student network by feding saved logits to student newtwork
---

## PreLab02

- **Topics**:
    - Implementing a method to achieve a Gaussian distribution using the Central Limit Theorem (CLT).
    - Implementing digital filtering and comparing results with MATLAB’s built-in `filter` function.
    - Determining the start of data transmission using correlation and a predefined header.
    - Visualizing the FFT of a single-tone signal and analyzing how various parameters (e.g., sample size, input frequency) affect the FFT output.

<div style="display: flex; justify-content: space-between;">
  <img src='Images/preLab02-01.jpg' alt="Gaussian Distribution" style="width: 48%;">
  <img src='Images/preLab02-02.jpg' alt="FFT Visualization" style="width: 48%;">
</div>

---

## PreLab03

- **Topics**:
    - Using matrices to calculate the Discrete Fourier Transform (DFT) and signal spectrum.
    - Observing the impact of non-ideal transformations from intermediate-band to baseband.

<img src="Images/preLab03-01.jpg" alt="DFT Calculation" style="width: 48%;">
<img src="Images/preLab03-02.jpg" alt="Spectrum Analysis" style="width: 48%;">

---

## Lab01

- **Topics**:
    - Simulations related to white noise, filtering, baseband signals, and intermediate-band signals.

<img src="Images/lab01-01.jpg" alt="Lab01 Simulation" style="width: 50%;">

---

## Lab02

- **Topics**:
    - Implementing a transmission simulation. The goal is to send data packets through an ideal channel and detect them.

- **Main functions**:
    - `bitGenerator`: Generates bits for transmission.
    - `grayMatrixGenerator`: Generates Gray code matrix for encoding.
    - `pulseModulation`: Modulates bits with different pulse shapes (e.g., triangular).
    - `symbolDetection`: Detects symbols using correlators or matched filters.
    - `minDistanceDetector`: Detects symbols based on minimum distance.

- **Modulation schemes**:
    - PAM
    - PSK
    - QAM

***Note:*** FSK modulation (coherent and non-coherent) is implemented in `lab05.m`.

<img src="Images/lab02-01.jpg" alt="Transmission Simulation" style="width: 50%;">

---

## Lab03

- **Topics**:
    - A complete implementation of a communication system, transmitting data with added noise, time delay, and phase offset.
    - Bit Error Rate (BER) vs SNR curves were plotted and compared with MATLAB’s built-in functions.

<div style="display: flex; justify-content: space-between;">
  <img src='Images/lab03-01.jpg' alt="BER Curve" style="width: 48%;">
  <img src='Images/lab03-02.jpg' alt="Communication System" style="width: 48%;">
</div>

---

## Lab04

- **Topics**:
    - Implementing a simple example to get started with the **ADALM-PLUTO (PlutoSDR)**.
    - Transmitting and receiving data using the PlutoSDR, visualized with MATLAB plots.

- **Files**:
    - `example.m`: A basic code for initializing and working with PlutoSDR.
    - `lab04.m`: Implements the communication system from `lab03.m` on PlutoSDR.

<img src="Images/lab04-01.jpg" alt="PlutoSDR Example" style="width: 50%;">

---

## Lab05

- **Topics**:
    - Completion of `lab03.m` with added Frequency Shift Keying (FSK) modulation and simulation.

<img src="Images/lab05-01.jpg" alt="FSK Modulation" style="width: 50%;">

---

## Lab06

- **Topics**:
    - Hardware implementation of `lab05.m` using **ADALM-PLUTO (PlutoSDR)**. It builds upon `lab04.m` with updates for FSK modulation.

---

### How to Use

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/digital-communication-lab.git
    cd digital-communication-lab
    ```

2. Open MATLAB and navigate to the desired session folder (e.g., `PreLab01`, `Lab01`, etc.).

3. Run the MATLAB scripts from the command line or MATLAB editor.

---

### Contributions

This laboratory project was completed by:

- [Salar Safardoust](https://github.com/salar-sfd)
- [Fateme Jalili](https://github.com/fatemeJalili)


