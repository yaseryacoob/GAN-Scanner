## GAN Image detector UMD


## Description


The classifier was trained on a balanced dataset of 81400 images, 40800 authentic (FFHQ+CELEBHQ) and 40800 GAN generated (5100 from each of StyleGAN2-raw plus three compressions levels, 10,25,50, StyleGAN-ADA, StyleGAN Distillation and SAM.

<font size="-4">

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/faf8dcdde7744173f1eb54b26802d2f1ffd8ec3f-ag.json
</font>


## Detection Accuracy 

| DATASET  | Type  | Data Size | Detection Accuracy | Notes |
| :------------ |:---------------|:-----|:-----|:-----|
| [MFC19-20](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91% | Real-world diversity|
| [UMD-BLEND](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91% | Real-world diversity|
| [FFHQ-Extention](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91% | Real-world diversity|
| [SAM](https://github.com/yuval-alaluf/SAM) | StyleGAN2 |14K        |   97% |  StyleGAN2-latentspace|
| [NAVIGAN](https://github.com/yandex-research/navigan) | StyleGAN2 | 8K | 99%|StyleGAN2-latentspace|
| [StyleMixing](https://arxiv.org/abs/2003.03581)| 93K|61%| STyleGAN2|
| [StyleGAN-ADA/CELEBHQ](https://github.com/NVlabs/stylegan2-ada) | StyleGAN2        | 5.3K | 65% |StyleGAN2-varient|
| [MobileStyleGAN](https://arxiv.org/abs/2104.04767)| StyleGAN2-reduced| 5K | 42% |StyleGAN2-varient|
| [CIPS](https://github.com/saic-mdal/CIPS)|GAN|3.5K|80%|Non-CNN, positional Encoding|
| [StyleGAN3](https://nvlabs.github.io/alias-free-gan/)|Detection|Images|Image returned as Evidence|Missing AAG|




## Take into account:

1. This is Research Code, there is no liability for use or guarantee of performance 
2. A Docker-based deployment (currently tested on linux based systems)
4. This Software requires access to GPU 


## Related Work
1. [NIST Media Forensic Challenge](https://mfc.nist.gov/#pills-overview)
2. [Only a Matter of Style: Age Transformation Using a Style-Based Regression Model, SIGGRAPH 2021](https://github.com/yuval-alaluf/SAM)
3. [Encoding in Style: a StyleGAN Encoder for Image-to-Image Translation, CVPR 2021](https://github.com/eladrich/pixel2style2pixel)
4. [StyleGAN2 Distillation for Feed-forward Image Manipulation,ECCV2020](https://arxiv.org/abs/2003.03581)
5. [MobileStyleGAN: A Lightweight Convolutional Neural Network for High-Fidelity Image Synthesis](https://arxiv.org/abs/2104.04767)
6. [Training Generative Adversarial Networks with Limited Data](https://github.com/NVlabs/stylegan2-ada)
7. [Image Generators with Conditionally-Independent Pixel Synthesis](https://github.com/saic-mdal/CIPS)
9. [Navigating the GAN Parameter Space for Semantic Image Editing, CVPR 2021] (https://github.com/yandex-research/navigan)
10. [Alias-Free Generative Adversarial Networks](https://nvlabs.github.io/alias-free-gan/)


### Latentgan StyleGAN2
<img src="./latentgan.png">




