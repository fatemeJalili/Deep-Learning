# Deep-Learning

This repository contains the code and documentation for the Neural Networks course homework assignments. Each folder represents a specific paper implementation. Below is a list of Homeworks along with a brief description of their contents.

## Homework 1

- Part 1: Implemented and trained **Adaline** and **Madaline** networks on a moon-shaped dataset.

  <div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/user-attachments/assets/85d6e45a-31c2-4008-a5b1-823528f70329" width="250">
    <img src="https://github.com/user-attachments/assets/2ba4384e-2a9d-4407-8258-83f264157ea2" width="250">
    <img src="https://github.com/user-attachments/assets/e0fec43f-8fb9-44a8-a823-7f0aaeaff5a1" width="250">
  </div>

- Part 2: Implemented a **Deep Autoencoder** to reduce data dimensions before **clustering** using the **k-means** algorithm. \
  <small>
  *This project implements the methodology described in [DAC: Deep Autoencoder-based Clustering, a General Deep Learning Framework of Representation Learning](https://arxiv.org/abs/2102.07472) by Si Lu and Ruisi Li.*
  <small>
  
  <div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/user-attachments/assets/80fdd936-bdef-4f95-afa1-b9fe65c91060" width="450">
  </div>

- Part 3: **Knowledge distillation** from the **teacher to the student network** by feeding saved logits to the student network.
  
  <div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/user-attachments/assets/ab53ef02-7982-4bae-88b0-5aab77b76651" width="350">
  </div>

## Homework 2
- Part 1: Conducted a comparative analysis between the **AlexNet** and **VGGNet** architectures for  an Eight-class Emotion Classification system, Incorporated techniques such as **Data Augmentation** and **Fine Tuning** to enhance performance. \
  <small>
  *This project implements the methodology described in [CNN-based Facial Affect Analysis on Mobile Devices](https://arxiv.org/abs/1807.08775) by Charlie Hewitt and Hatice Gunes.*
  <small>
  <div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/user-attachments/assets/3c4b314a-f841-4b63-ad49-b66709d2da74" width="300">
    <img src="https://github.com/user-attachments/assets/0e151b62-0217-4022-81c1-a3b2b4455f6a" width="300">
  </div>

- Part 2: Developed a **CNN** model for COVID-19 disease detection based on x-ray image classification. \
  <small>
  *This project implements the methodology described in [An Efficient CNN Model for COVID-19 Disease Detection Based on X-Ray Image Classification](https://onlinelibrary.wiley.com/doi/10.1155/2021/6621607) by Aijaz Ahmad Reshi and Furqan Rustam.*
  <small>

  <img src="https://github.com/user-attachments/assets/c20e2124-37ca-447e-b632-094fa88517ce" width="600"> \
  <img src="https://github.com/user-attachments/assets/0c0aedab-d7c1-4918-bfb9-f0d7414c563b" width="300">

## Homework 3
- Part 1: Fine-tuning the **SAM model** for **semantic segmentation** on waterbody satellite images by **freezing** the image encoder and prompt encoder parts. \
  <small>
  *This project implements the methodology described in [Segment Anything](https://arxiv.org/pdf/2304.02643.pdf) by Alexander Kirillov and Eric Mintun.*
  <small>

  <img src="https://github.com/user-attachments/assets/73586f4c-d77b-44bd-8677-b88ab7293aa7" width="400">
- Part 2: Implemented the **Faster R-CNN** model to detect fire and draw bounding boxes. \
  <small>
  *This project implements the methodology described in [Analysis of Object Detection Performance Based on Faster R-CNN](https://iopscience.iop.org/article/10.1088/1742-6596/1827/1/012085/meta) by Wenze Li.*
  <small>
  
   <img src="https://github.com/user-attachments/assets/e84a1b80-6293-4739-8567-c35d0c4a0556" width="500"> \
   <img src="https://github.com/user-attachments/assets/42e5a134-ee1a-4bc7-bc74-3b2bf6dd76f5" width="350"> 

## Homework 4
- Part 1: Predicting the future value of a stock using different architectures, such as **RNN, LSTM, GRU**, and **Conv-LSTM**. \
  <small>
  *This project implements the methodology described in [The Performance of LSTM and BiLSTM in Forecasting Time Series](https://ieeexplore.ieee.org/document/9005997) by Sima Siami-Namini and Neda Tavakoli.*
  <small>
  
- Part 2: Implemented **CNN + 2 layer LSTM** model for predicting suisaidal thoughts through twitter datas. \
  <small>
  *This project implements the methodology described in [Stacked CNN - LSTM approach for prediction of suicidal ideation on social media](https://link.springer.com/article/10.1007/s11042-023-14431-z) by Bhavini Priyamvada and Shruti Singhal.*
  <small>

   <img src="https://github.com/user-attachments/assets/c68fa56e-88ff-4ccd-8e02-e9818f093f86" width="600"> 

## Homework 5
- Part 1: Implemented the **HuBERT**, **self-supervised** model for speech emotion recognition. \
  <small>
  *This project implements the methodology described in [HuBERT: Self-Supervised Speech Representation Learning by Masked Prediction of Hidden Units](https://ieeexplore.ieee.org/abstract/document/9585401) by Wei-Ning Hsu and Benjamin Bolte.*
  <small>

   <img src="https://github.com/user-attachments/assets/0df6e613-f6fe-4087-bbf0-340aec51101e" width="400"> 

- Part 2: **Fine-tuned** the large pre-trained **transformer** model, **BERT**, and analyzed the impact of different techniques such as **freezing** and **pruning**. \
  <small>
  *This project implements the methodology described in [Are Sixteen Heads Really Better than One?](https://arxiv.org/abs/1905.10650) by Paul Michel and Omer Levy and [What Would Elsa Do? Freezing Layers During Transformer Fine-Tuning](https://arxiv.org/abs/1911.03090) by Jaejun Lee and Raphael Tang.*
  <small>
  
   <img src="https://github.com/user-attachments/assets/6d850fba-93a4-4b73-98f7-e5e66f919377" width="400"> 

## Homework 6
- Part 1: Implemented Control VAE model
  <small>
  *This project implements the methodology described in [ControlVAE: Controllable Variational Autoencoder](https://arxiv.org/abs/2004.05988) by Huajie Shao and Shuochao Yao.*
  <small>

  <img src="https://github.com/user-attachments/assets/f33180ba-1e0a-4f47-a171-d25c631ae648" width="350"> 

- Part 2: Implemented **GAN**, **Wasserstein GAN** and **self-supervised GAN** models on MINST data set. \
  <small>
  *This project implements the methodology described in [Wasserstein GAN](https://arxiv.org/abs/1701.07875) by Martin Arjovsky and Soumith Chintala and [Self-Supervised GANs via Auxiliary Rotation Loss](https://arxiv.org/abs/1811.11212) by Ting Chen and Xiaohua Zhai.*
  <small>
  <div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/user-attachments/assets/19385315-1562-461d-bb32-1fb2b49eb93d" width="250">
    <img src="https://github.com/user-attachments/assets/e1d97141-0976-4f32-8685-39d78e007a55" width="250">
    <img src="https://github.com/user-attachments/assets/175ee70c-1d5c-48bf-b0aa-fd0508b71bf8" width="250">
  </div>

  ## Homework 7:
  - Part 1: Fine-tuned the **RoBERTa** model using **Low-Rank Adaptation (LoRA)** of **large language models**.
    <small>
  *This project implements the methodology described in [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) by HEdward J. Hu and Yelong Shen.*
    <small>

    <img src="https://github.com/user-attachments/assets/2d6a3a4a-56ef-4956-9506-82631a9c08b8" width="400"> 




