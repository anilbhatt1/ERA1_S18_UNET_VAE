
<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![MIT License][license-shield]][license-url]

## UNET and VAE
________

<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Prerequisites](#prerequisites)
* [Code](#Code)
* [License](#license)

## Prerequisites

* [Python 3.8](https://www.python.org/downloads/) or Above
* [Pytorch 1.8.1](https://pytorch.org/)  
* [Google Colab](https://colab.research.google.com/)

<!-- Code -->
## Code
- **Dataset Used for VAE** : MNIST , Image Resolution : 28x28x1 , CIFAR-10, Image Resolution : 32x32x3
- For Training details of **MNIST VAE**, refer below colab notebook locations:
    - Takes in two inputs:
        - an MNIST image, and
        - its label (one hot encoded vector sent through an embedding layer)
        - Passes one-hot label as input to model and uses torch.add to concatenate image tensor & one-hot label tensor. 
File : ERA1_S18_MNIST_VAE_V0.ipynb
- For Training details of **CIFAR-10 VAE**, refer below colab notebook locations:
    - Takes in two inputs:
        - a cifar10 image, and
        - its label (one hot encoded vector sent through an embedding layer)
File : ERA1_S18_CIFAR10_VAE_V0.ipynb
- **Dataset Used for UNET** : OxfordIIITPet
- For Training details of , refer below colab notebook locations:
    - MP + TransposeConv + BCE
        File : ERA1_S18_UNET_mptrbce.ipynb
    - MP + TransposeConv + Dice Loss
        File : ERA1_S18_UNET_mptrdice.ipynb
    - StridedConv + TransposeConv + BCE
        File : ERA1_S18_UNET_strtrbce.ipynb
    - StridedConv + Upsampling + BCE
        File : ERA1_S18_UNET_strUpsbce.ipynb
<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=flat-square
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=flat-square
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=flat-square
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=flat-square
[license-url]: https://github.com/anilbhatt1/Deep_Learning_EVA4_Phase2/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555




