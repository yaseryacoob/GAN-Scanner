## GAN-Scanner, a GAN Image Detector 

<img src="./data/seed39942_300_95.jpg" height="280"><img src="./data/seed48305_640_80.jpg" height="280"> <img src="./data/seed48321_384_95.jpg" height="280">

This page describes a GAN image detector developed at Computer Vision Lab, University of Maryland, College Park.

## Description

This detector is designed for faces. It works best at medium and high resolution images (128x128 and higher).

This detector employs StyleGAN2 inversion as the core-idea for detection. The hypothesis is that a perfect inversion of a face is highly likely to be a GAN generated image, while a real-image is slightly less invertable. Multiple metrics are used to compute a feature vector that reflects the outome of the inversion. This computed feature is classified (0 to 1.0, where 0 is likely a GAN image image and 1.0 is an authentic image). An evidence image is provided to help a human make determine if the processing is credible.

The classifier was trained on a balanced dataset of 81400 images, 40800 authentic (FFHQ+CELEBHQ) and 40800 GAN generated (5100 from each of StyleGAN2-raw plus three compressions levels, 10,25,50, StyleGAN-ADA (inversions of StyleGAN2 and CELEBHQ), StyleGAN2 Distillation and SAM (see references at the bottom).


## Request Code or Data 

Please fill out the [Form](https://docs.google.com/forms/d/e/1FAIpQLSd-q3XZmHlvPxZOP8nwFi8Q8cl4epx8HyWrx5ApOszj8g-wnA/viewform) if you are interested in the software.  Please note that access will be granted to "image-consuming entities for public interest". Individuals (including students and researchers), re-packagers, as well as opaque entities will not be granted access. 

For any questions or feedback, please e-mail yaser@umd.edu with the subject [Question about the GAN-Scnanner].

## ROC of the Classifier

The trained classifier is shown, in the graph below,  under two configurations. The full face configuration assumes that the face is fully visible with a reasonable background area. The second configuration  assumes that the face may be partially obsecured, either due to photo composition or partial occlusion (for example in a multi-person scene). The performance charactersitics deteriorate sightly. From AUC of 0.91 to 0.88. 


### 
<img src="./data/GAN_CLASSIFIER.png" width="300">

## Open-World Detection Accuracy 
Several targeted experiments were conducted to determine how GAN-Scanner performs in an open-world environment. Three datasets of real images were used, to assess performance under different/unknown data distributions. 
[MFC 19-20](https://mfc.nist.gov/#pills-overview) is NIST collected dataset for Forenisc Analysis. UMD-BLEND is derived from over 50K images, consisting of IARPA JANUS-CS3 Face Recogniton dataset,
[FaceBook Fairness Dataset](https://ai.facebook.com/blog/shedding-light-on-fairness-in-ai-with-a-new-data-set),
Boston and Marine Corp Marathons, flicker-based Dataset (UMD), and Women's March in DC Flicker Dataset (UMD). Finally, FFHQ-Extension is a 27K images unreleased FFHQ-sourced from Nvidia's original collection (these were released for this specific detection task).

The GAN generators varied, between  StyleGAN2-related algorithms (these strongly operate in the same latent space), mixed or significant variants of StyleGAN2,  non CNN architectures as well as StyleGAN3.
The following detection accuracy reflects open-world performance of GAN-Scanner.


| DATASET  | Type  | Data Size | Detection Accuracy1| Detection Accuracy2 | Notes |
| :------------ |:------------------|:----|:----|:----|:--------|
| [MFC19-20](https://mfc.nist.gov/#pills-overview)  | Real Data | 7.6K | 95.1%|93.3% | Real-world diversity|
| [UMD-BLEND](https://mfc.nist.gov/#pills-overview)  | Real Data | 21K | 93.6%|85.0% | Real-world diversity|
| [FFHQ-Extension](https://mfc.nist.gov/#pills-overview)  | Real Data | 27K | xx%|xx% | Real-world diversity|
| [SAM](https://github.com/yuval-alaluf/SAM) | StyleGAN2 |13.8K        |   98.4%|96.4% |  StyleGAN2-latentspace|
| [NAVIGAN](https://github.com/yandex-research/navigan) | StyleGAN2 | 8.4K | 99.8%|99.2%|StyleGAN2-latentspace|
| [StyleMixing](https://arxiv.org/abs/2003.03581)| StyleGAN2+Pix2pix | 93.4K|42.2%|55.8%| StyleGAN2+Pix2Pix|
| [MobileStyleGAN](https://arxiv.org/abs/2104.04767)| StyleGAN2-reduced| 5K | 42%|37.8% |StyleGAN2-varient|
| [CIPS](https://github.com/saic-mdal/CIPS)|GAN|7K|63.2%|76.5%|Non-CNN, positional Encoding|
| [StyleGAN3](https://nvlabs.github.io/alias-free-gan/)|StyleGAN3|||||




## Notes

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






