# Overview
The objective of this project is to explore the deep learning model’s ability to mimic the Rietkerk’s PDE model in generating the vegetation image dynamics. 
Therefore, the CNN-LSTM GAN model is constructed that extracts the key features of each consequtive timepoint input images and establishes the temporal relationship across input images. The evaluation of the generated images is conducted by the discriminator, a multi-layers CNN model. 

This capstone project proposes an innovative objective formula, the Least Squares Mean Squared Loss (LS-MSE) that modified from the traditional least squares loss. This proposed objective formula aims to directly compare the generated image data to the real data by adding the MSE term in the generator loss, calculating the average squared pixel differences between the generated and real images. In addition, the added MSE term may provide additional information for the CNN-LSTM model for the backpropagation stage. The results demonstrate that the CNN-LSTM trained under LS-MSE outperforms either the Wasserstein loss with gradient penalty (WGAN-GP) or the least
squares loss (LSGAN).

# Generator: CNN-LSTM
The generator ($G$) is a deep learning model composed of an encoder and a decoder.  The encoder processes input images from $t_{0}$ to $t_{6}$, using a 5-layer CNN and a 4-layer bidirectional LSTM. The encoder’s output is then fed into the 5-layer transpose CNN (the decoder) to generate predicted images at $t_{7}$.The quality of the generated images is assessed by the discriminator, a multilayers CNN.
