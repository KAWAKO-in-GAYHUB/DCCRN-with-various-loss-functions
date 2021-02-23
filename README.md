# DCCRN with various loss functions

DCCRN(Deep Complex Convolutional Recurrent Network) is one of the deep neaural networks proposed at [[1]](https://arxiv.org/abs/2008.00264). This repository is an application using DCCRN with various loss functions. Our original paper can be found here, and you can check the test samples here.   
<br>   
   
![DCCRN_수정최종](https://user-images.githubusercontent.com/55497506/105969652-d39f6b80-60cb-11eb-805c-0f204405ef37.png)
> Source of the figure: [Performance comparison evaluation of speech enhancement using various loss function.]()   
<br>



# Loss functions
We use two base loss functions and two perceptual loss functions.

> Base
  1. MSE: Mean Squred Error   
  ![image](https://user-images.githubusercontent.com/55497506/106714015-97758900-663e-11eb-9593-6ecfd4266a41.png)
  <br>

  2. SI-SNR: Scale Invariant Source-to-Noise Ratio   
  ![image](https://user-images.githubusercontent.com/55497506/106714206-da376100-663e-11eb-94c6-77f6588616b9.png)
  <br>

> Perceptual
  1. LMS: Log Mel Spectra   
  ![image](https://user-images.githubusercontent.com/55497506/106714238-e58a8c80-663e-11eb-8601-58bb020a2d3b.png)
  <br>

  2. PMSQE: Perceptual Metric for Speech Quality Evaluation   
  ![image](https://user-images.githubusercontent.com/55497506/106714147-c855be00-663e-11eb-8a8d-a9d5aba1325d.png)
  <br>


# Requirements
> This repository is tested on Ubuntu 20.04.
* Python 3.7+
* Cuda 10.0+
* CuDNN 7+
* Pytorch 1.7+
<br>

> Library
* 

# Prepare data
The training data consists of the following three dimensions.   
```[Batch size, 2(input & target), wav length]``` 
<br>
The test data consists of the following dimensions.   
```[2(noise type: seen, unseen), dB classes, Batch size, 2(input & target), wav length]```

<br>
We cut the wav files longer than 3 seconds into 3 seconds and zero padded for wav files shorter than 3 seconds.   
The sampling frequency is 16k.

# Use pretrained models
If you want to test the model described in the [paper](), you can change chkpt_model path in ```config.py``` like ```'SI-SNR/'```  
<br>
We have uploaded 3 models trained with each loss function, SI-SNR, SI-SNR + LMS and SI-SNR + PMSQE.   

# Performance evaluation
**Objective evaluation**
> The performance table of various loss functions using seen noise. 
<br>
> The performance table of various loss functions using unseen noise.
<br>   

**Spectrogram**   
![image](https://user-images.githubusercontent.com/55497506/108705017-1a0fab00-7550-11eb-962a-9f0b218371a8.png)   
> Source of the figure: [Performance comparison evaluation of speech enhancement using various loss function.]()   
> The spectrograms of  (a) clean speech, (b) noisy speech at 0 dB SNR, estimated speeches using (c)  MSE and PMSQE, (d)  SI-SNR , (e) SI-SNR and PMSQE, (f)  SI-SNR and LMS.

# References
**DCCRN: Deep Complex Convolution Recurrent Network for Phase-Aware Speech Enhancement**   
Yanxin Hu, Yun Liu, Shubo Lv, Mengtao Xing, Shimin Zhang, Yihui Fu, Jian Wu, Bihong Zhang, Lei Xie   
[[arXiv]](https://arxiv.org/abs/2008.00264)  [[code]](https://github.com/huyanxin/DeepComplexCRN)


# Paper
[Performance comparison evaluation of speech enhancement using various loss function.]()
