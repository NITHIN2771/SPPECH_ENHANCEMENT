Spectrogram-Based Speech Enhancement using Temporal-Aware 3D-CNN & Recurrent Fusion


INTRODUCTION :

This project developed an advanced speech enhancement system designed to improve the quality and intelligibility of noisy speech. Traditional 2D-CNN or RNN models process spectrograms frame-by-frame and often fail to capture long-range temporal patterns.

To address this, our model combines:

 1. Temporal-Aware 3D-CNN → learns both spectral and temporal structures across multiple frames

 2. GRU-based Recurrent Fusion → models long-term dependencies and improves speech continuity

    This hybrid architecture results in superior noise suppression, especially under non-stationary noise (babble, traffic, interfering speech).



WORKING PRINCIPLE :

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



IMPLEMENTATION DETAILS:

Technologies & Libraries :

1. Python

2. PyTorch / TensorFlow (depending on your setup)

3. Librosa for audio processing

4. NumPy, Matplotlib, SciPy

Model Components :

1. Six 3D-CNN layers with Leaky ReLU activation

2. 3D Max-Pooling for downsampling

3. Fully connected bottleneck layer

4. GRU-based recurrent fusion block

5. Spectrogram reconstruction layer



📈 RESULTS :

Our Temporal-Aware 3D-CNN with Recurrent Fusion outperforms several baselines such as:

1. DNN

2. U-Net

3. ResU-Net

4. Transformer-based models

5. Attention-enhanced architectures

KEY IMPROVEMENTS:

  1. Higher STOI and PESQ

  2. Cleaner speech in heavy noise

  3. Better preservation of speech structure

  4. Strong robustness to non-stationary and speech-like noise



APPLICATIONS :

  1. Voice-controlled systems

  2. Hearing aids

  3. Real-time communication

  4. Teleconferencing

  5. Speech recognition pre-processing
