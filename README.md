
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
    - File : ERA1_S18_MNIST_VAE_V0.ipynb 
        - Link : https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/blob/master/ERA1_S18_MNIST_VAE_V0.ipynb
        - Takes in two inputs:
            -   an MNIST image, and
            -   its label (one hot encoded vector sent through an embedding layer)
        - Passes one-hot label as input to model encoder 
        - Uses torch.add inside encoder to concatenate image tensor & one-hot label tensor. 
        - Results

            ![MNIST_VAE_RESULTS_V0](https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/assets/43835604/21574a86-9c03-408d-9614-897cd1ba14a7)


    - File : ERA1_S18_MNIST_VAE_V1.ipynb 
        - Link : https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/blob/master/ERA1_S18_MNIST_VAE_V1.ipynb
        - Takes in two inputs:
            -   an MNIST image, and
            -   its label (one hot encoded vector sent through an embedding layer)
        - One-hot label changed to 28x28
        - If actual label is 2, then column 3 in 28x28 grid will be given a value of 1. 
        - This 28x28 tensor is added to the 28x28 image tensor 
        - Combined tensor passed to the model encoder
        - This 28x28 one-hot tensor is also reshaped to 784 and passed to the decoder
        - Through a FC layer this is downsized to 256 and combined with encoder output
        - Results

            ![MNIST_VAE_RESULTS_V1](https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/assets/43835604/20475c66-0d2b-4f36-9e57-75b8b17c0068)

          
    - File : ERA1_S18_MNIST_VAE_V2.ipynb 
        - Link : https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/blob/master/ERA1_S18_MNIST_VAE_V2.ipynb
        - Takes in two inputs:
            -   an MNIST image, and
            -   its label (one hot encoded vector sent through an embedding layer)
        - One-hot label changed to 28x28
        - If actual label is 2, then column 3 and column 4 in 28x28 grid will be each given value of 0.5. 
        - This 28x28 tensor is reshaped to 784 and passed to the decoder ONLY
        - Through a FC layer this is downsized to 256 and combined with encoder output         
        - Results
          
             ![MNIST_VAE_RESULTS_V2](https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/assets/43835604/719953c7-4502-45bd-9d5f-a46d36f551f2)

             
    - File : ERA1_S18_MNIST_VAE_V3.ipynb 
        - Link : https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/blob/master/ERA1_S18_MNIST_VAE_V3.ipynb
        - Takes in two inputs:
            -   an MNIST image, and
            -   its label (one hot encoded vector sent through an embedding layer)
        - One-hot label changed to 28x28
        - If actual label is 2, then column 3 and column 4 in 28x28 grid will be each given value of 0.5. 
        - This 28x28 tensor is added to the 28x28 image tensor 
        - Combined tensor passed to the model encoder
        - The 28x28 one-hot tensor is also reshaped to 784 and passed to the decoder
        - In decoder , through a FC layer this is downsized to 256 and combined with encoder output
        - Results
 
             ![MNIST_VAE_RESULTS_V3](https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/assets/43835604/63ebba75-9aa1-4e7b-8a48-0862d72d49e0)

    - File : ERA1_S18_MNIST_VAE_V4.ipynb 
        - Link : https://github.com/anilbhatt1/ERA1_S18_UNET_VAE/blob/master/ERA1_S18_MNIST_VAE_V4.ipynb
        - Takes in two inputs:
            -   an MNIST image, and
            -   its label (one hot encoded vector sent through an embedding layer)
        - One-hot label changed to 28x28
        - If actual label is 2, then column 4 and column 5 in 28x28 grid will be each given value of 0.5. 
        - This 28x28 tensor is added to the 28x28 image tensor 
        - Combined tensor passed to the model encoder
        - The 28x28 one-hot tensor is also reshaped to 784 and passed to the decoder
        - In decoder , through a FC layer this is downsized to 256 and combined with encoder output
        - Results

- For Training details of **CIFAR-10 VAE**, refer below colab notebook locations:
    - File : ERA1_S18_CIFAR10_VAE_V0.ipynb
        - Takes in two inputs:
            - a cifar10 image, and
            - its label (one hot encoded vector of [10] sent through an embedding layer)
            - passed only to Encoder
    - File : ERA1_S18_CIFAR10_VAE_V1.ipynb
        - Takes in two inputs:
            - a cifar10 image, and
            - its label (one hot encoded vector of [10] sent through an embedding layer)
            - This one-hot label is reshaped to (32, 32, 3) and labels changed.
            - If actual label is 2, then column 3 and column 4 in 32x32 grid will be each given value of 0.5. 
            - This 32x32x3 tensor is then added to the 32x32x3 image tensor 
            - Combined tensor passed to the model encoder
            - Results

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




