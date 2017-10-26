# cnn-medical-image-segmentation

This project applies fully convolutional network for a medical image segmentation problem. For more detail on the challenge, please visit https://www.kaggle.com/c/ultrasound-nerve-segmentation

I implemented a CNN network to learn 70*116 labeled images. The original image and mask have size 420*580, but typically a defect has size around 80*80, so I chose the above small-size images. The CNN has two convolutional blocks to reduce
70*116 -> 35*58 -> 7*29.

After we learned the defect pattern from the CNN network, I implemented a corresponding FCN network to learn pixel-wise segmentation in each 70*116 images. The FCN makes modification on the CNN by changing dense layers into convolutional layers and ignoring the final prediction layer. Moreover, it add previous pooling layer weights to the upsampled final convolutional layer weights. In order to add up weights from different layers as well as scale back to the input size image, we need to use deconvolutional layers or upsampling technique.

The work is done in keras with tensorflow backend.

First read Data_preprocessing to setup the data folders and files, then read Simplified_FCN.ipynb

### please read Simplified_FCN.ipynb

