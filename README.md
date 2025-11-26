Spectrogram-Based Speech Enhancement using Temporal-Aware 3D-CNN & Recurrent Fusion
📌 Introduction

This project developed an advanced speech enhancement system designed to improve the quality and intelligibility of noisy speech. Traditional 2D-CNN or RNN models process spectrograms frame-by-frame and often fail to capture long-range temporal patterns.

To address this, our model combines:

Temporal-Aware 3D-CNN → learns both spectral and temporal structures across multiple frames

GRU-based Recurrent Fusion → models long-term dependencies and improves speech continuity

This hybrid architecture results in superior noise suppression, especially under non-stationary noise (babble, traffic, interfering speech).

⚙️ How It Works (System Workflow)

The overall workflow consists of the following stages:

1. Preprocessing

Input noisy speech is converted to a spectrogram using Short-Time Fourier Transform (STFT).

This produces a time-frequency representation suitable for deep learning.

2. Temporal-Aware 3D-CNN

Spectrogram frames are stacked into 3D blocks.

3D convolution layers extract spectral–temporal features from multiple consecutive frames, unlike 2D-CNNs.

This helps the model understand speech continuity and dynamic noise behavior.

3. Recurrent Fusion Module (GRU)

Selected feature maps from different CNN layers are fused.

A GRU network learns long-term temporal relationships and enhances speech structure.

This step prevents over-smoothing and preserves speech clarity.

4. Reconstruction

Enhanced features are converted back into a refined spectrogram.

Inverse STFT (iSTFT) reconstructs the enhanced time-domain speech waveform.

🛠 Implementation Details
Technologies & Libraries

Python

PyTorch / TensorFlow (depending on your setup)

Librosa for audio processing

NumPy, Matplotlib, SciPy

Model Components

Six 3D-CNN layers with Leaky ReLU activation

3D Max-Pooling for downsampling

Fully connected bottleneck layer

GRU-based recurrent fusion block

Spectrogram reconstruction layer


📈 Results

Our Temporal-Aware 3D-CNN with Recurrent Fusion outperforms several baselines such as:

DNN

U-Net

ResU-Net

Transformer-based models

Attention-enhanced architectures

Key Improvements

Higher STOI and PESQ

Cleaner speech in heavy noise

Better preservation of speech structure

Strong robustness to non-stationary and speech-like noise

🎯 Applications

Voice-controlled systems

Hearing aids

Real-time communication

Teleconferencing

Speech recognition pre-processing
