# OCT Image Processing and Classification

Welcome to the OCT Image Processing and Classification project!
Step into the world of ophthalmology, where Optical Coherence Tomography (OCT) rules diagnosis. OCT isn't just a fancy imaging technique; it's a game-changer in diagnosing and treating eye conditions. Think Age-related Macular Degeneration (AMD), Diabetic Retinopathy (DR), and Diabetic Macular Edema (DME) – OCT sees them all.But it's not just about taking pretty pictures. OCT gives us a close-up view of the retina's inner workings, helping doctors tailor treatments and catch issues early. That's why we're obsessed with getting the clearest, most detailed OCT images possible. It's not just about the tech – it's about making sure we can spot problems before they get serious.
This project involves three main components:

1.⁠ ⁠*Denoising*: OCT images are denoised using CycleGANs.

2.⁠ ⁠*Super-Resolution*: Denoised images are enhanced using ESRGAN for super-resolution.

3.⁠ ⁠*Volumetric Classification*: Super-resolved images are classified using a 3D CNN architecture.

## Table of Contents
•⁠  ⁠[Project Overview](#project-overview)

•⁠  ⁠[Methods](#methods)

  - [Denoising with CycleGANs](#denoising-with-cyclegans)
    
    - [Super-Resolution with ESRGAN](#super-resolution-with-esrgan)
    
    - [Volumetric Classification with 3D CNN](#volumetric-classification-with-3d-cnn)
    
•⁠  ⁠[Data](#data)

•⁠  ⁠[Setup](#setup)

•⁠  ⁠[Usage](#usage)

•⁠  ⁠[Results](#results)

•⁠  ⁠[Conclusion](#conclusion)

•⁠  ⁠[License](#license)

## Project Overview

This project demonstrates a comprehensive approach to processing and classifying optical coherence tomography (OCT) images. By combining denoising, super-resolution, and classification techniques, we aim to improve the quality and accuracy of medical imaging analysis.

## Methods

### Denoising with CycleGANs
•⁠  ⁠*Description*: OCT images often contain noise that can hinder analysis. We employ CycleGANs to denoise these images effectively.

•⁠  ⁠*Details*: The CycleGAN model is trained using unpaired datasets to learn how to translate noisy images to denoised ones.where as the preliminary step we have used the median filter to remove noise then we have applied cycle gans for noise removal such that we feed the filtered image to one generator and non filtered image to the other generator.

### Super-Resolution with ESRGAN
•⁠  ⁠*Description*: After denoising, we enhance the images using ESRGAN to achieve super-resolution.

•⁠  ⁠*Details*: The ESRGAN model is trained on pairs of low-resolution and high-resolution images to produce high-quality super-resolved images.Here the intial layer does the feature extreaction, the middle block has upsampling layer has transpose convolution with leaky relu activation finally the third block has the image reconstruction block to give us the super resolved image.

### Volumetric Classification with 3D CNN
•⁠  ⁠*Description*: We classify volumetric OCT images using a 3D CNN architecture.

•⁠  ⁠*Details*: The 3D CNN model is trained to classify images into different categories based on their volumetric features.Here we have used a 3D CNN model where we have fed it images of depth 3 that a single grayscale image is a combination of three grayscale images stacked together then finally the images are classified into the following three categories a)Normal b)Diabetic c)Non-Diabetic.

## Data

•⁠  ⁠*Dataset*: The dataset that we are working is divided into three classes namely diabetic, normal and non-diabetic patient. Inside each class we have the folders corresponding to a particular patient with oct scans taken at different angles and this number of angles is also variable depending on the number of images in that folder for that patient.

## Setup

To set up the project, follow these steps:
1.⁠ ⁠Clone the repository:
    ⁠ bash
    git clone https://github.com/yourusername/yourrepository.git
    cd yourrepository
     ⁠

2.⁠ ⁠Install required packages:
    ⁠ bash
    pip install -r requirements.txt
     ⁠

3.⁠ ⁠Download or prepare the dataset as described in the [Data](#data) section.

4.⁠ ⁠Set up the project according to the documentation provided in the respective method sections.

## Usage

•⁠  ⁠*Denoising*:
    ⁠ bash
    python denoise.py --input <input_folder> --output <output_folder>
     ⁠

•⁠  ⁠*Super-Resolution*:
    ⁠ bash
    python super_resolution.py --input <input_folder> --output <output_folder>
     ⁠

•⁠  ⁠*Volumetric Classification*:
    ⁠ bash
    python classify.py --input <input_folder>
     ⁠

## Results

•⁠  ⁠*Result of Denoising*:
    
     ⁠

•⁠  ⁠*Result of Super-Resolution*:
    ⁠ bash
    python super_resolution.py --input <input_folder> --output <output_folder>
     ⁠

•⁠  ⁠*Result of Volumetric Classification*:
    ⁠ bash
    python classify.py --input <input_folder>

## Conclusion

In conclusion, the use of machine learning models such as CycleGANs, super-resolution networks, and 3D CNNs for processing and analyzing OCT images has proven to be a successful approach for advancing medical imaging research. The CycleGAN model effectively denoised the OCT images, removing artifacts and enhancing image quality without the need for paired training data. Following the denoising process, the super-resolution model significantly improved the resolution and detail of the images, enabling better visualization and analysis. Finally, the 3D CNN model demonstrated robust performance in volumetric classification, successfully distinguishing between different classes of medical conditions based on the enhanced OCT scans.

## License

we will provide it later.
---

We hope you find this project useful and welcome contributions and feedback! Feel free to open an issue or pull request if you have any suggestions or improvements.
