# Monet_GAN_Project

GAN Monet Style Transfer

This project is a submission to the Kaggle Competition: https://www.kaggle.com/c/gan-getting-started/overview . The objective of this competition was to generate Monet-style images using Generative Adversarial Networks (GANs).
Project Overview

The project involves:

    Building a CycleGAN to transform real photos into Monet-style paintings.
    Training the GAN on a dataset of Monet paintings and real-world photos.
    Generating 7,000–10,000 Monet-style images.
    Evaluating the model performance using MiFID (Memorization-informed Fréchet Inception Distance).
    Preparing the submission file with generated images.

Dataset

The dataset consists of:

    Monet Paintings:
        300 images in both JPEG and TFRecord formats.
    Real Photos:
        7,038 images in both JPEG and TFRecord formats.

Dataset source: Kaggle Competition Dataset.
Steps Performed
1. Data Preprocessing

    Loaded and preprocessed Monet paintings and photo datasets.
    Normalized images to the range [-1, 1] for GAN compatibility.
    Resized all images to 256×256256×256.

2. CycleGAN Architecture

    Generator:
        ResNet-based architecture with residual blocks for photo-to-Monet and Monet-to-photo transformations.
    Discriminator:
        PatchGAN architecture for fine-grained image classification.

3. Loss Functions

    Adversarial Loss: Helps generators create realistic images.
    Cycle Consistency Loss: Ensures that transformations are reversible.
    Identity Loss: Preserves colors and structure of images already in the target domain.

4. Training

    Used TensorFlow and Keras to implement and train the CycleGAN.
    Trained for 50 epochs with:
        Batch size: 8 (adjusted for GPU memory).
        Adam optimizer with learning rate: 2×10−42×10−4.
    Added checkpoints and progress logging for monitoring.

5. Generating and Saving Images

    Passed real photos through the trained generator to create Monet-style images.
    Saved 10,000 generated images as JPEG files.
    Packaged all images into a single images.zip file for submission.

6. Evaluation

    Computed MiFID (or FID) score to evaluate the similarity between generated images and real Monet paintings.

Results

    Successfully generated Monet-style images with artistic qualities resembling Monet’s works.
    Packaged the images into a submission file (images.zip) for evaluation.
