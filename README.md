## GAN Image detector UMD


## Description


The classifier was trained on a balanced dataset of 81400 images, 40800 authentic (FFHQ+CELEBHQ) and 40800 GAN generated (5100 from each of StyleGAN2-raw plus three compressions levels, 10,25,50, StyleGAN-ADA, StyleGAN Distillation and SAM.


## Request Code or Data 

Please fill out the [Form](https://docs.google.com/forms/d/1NtHP5eo25rceqnirmTmfdJ3e6nltyu0wNIuNBrFk29I/prefill) after reading and agreeing our License Agreement. For any questions or feedback, please e-mail yaser@umd.edu with the subject [Question about the GAN-Scnanner]. Please note that access will granted to image-consuming entities for public interest.Individuals (including students and researchers), re-packagers, as well as opaque entities will not be granted access.

<font size="-4">


</font>


## Detection Accuracy 

| DATASET  | Type  | Data Size | Detection Accuracy1| Detection Accurcy2 | Notes |
| :------------ |:---------------|:-----|:-----|:-----|:-------|
| [MFC19-20](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91%|91% | Real-world diversity|
| [UMD-BLEND](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91%|91% | Real-world diversity|
| [FFHQ-Extension](https://mfc.nist.gov/#pills-overview)  | Real Data | 8K | 91%|91% | Real-world diversity|
| [SAM](https://github.com/yuval-alaluf/SAM) | StyleGAN2 |14K        |   97%|91% |  StyleGAN2-latentspace|
| [NAVIGAN](https://github.com/yandex-research/navigan) | StyleGAN2 | 8K | 99%|91%|StyleGAN2-latentspace|
| [StyleMixing](https://arxiv.org/abs/2003.03581)| StyleGAN2+Pix2pix | 93K|61%|91%| StyleGAN2+Pix2Pix|
| [MobileStyleGAN](https://arxiv.org/abs/2104.04767)| StyleGAN2-reduced| 5K | 42%|91% |StyleGAN2-varient|
| [CIPS](https://github.com/saic-mdal/CIPS)|GAN|7K|80%|91%|Non-CNN, positional Encoding|
| [StyleGAN3](https://nvlabs.github.io/alias-free-gan/)|StyleGAN3|||||




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
8. [Navigating the GAN Parameter Space for Semantic Image Editing, CVPR 2021] (https://github.com/yandex-research/navigan)
9. [Alias-Free Generative Adversarial Networks](https://nvlabs.github.io/alias-free-gan/)


### Latentgan StyleGAN2
<img src="./latentgan.png">




