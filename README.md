# U-Net-Image-Segmentation
This is a project on image segmentation with U-net architecture on Oxford-IIIT pet dataset, available as part of the TensorFlow Datasets. The architecture was inspired by [U-Net: Convolutional Networks for Biomedical Image Segmentation.](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/)

---
# Overview
## Dataset
This tutorial uses the [Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) (Parkhi et al, 2012). The dataset consists of images of 37 pet breeds, with 200 images per breed (~100 each in the training and test splits). Each image includes the corresponding labels, and pixel-wise masks. The masks are class-labels for each pixel. Each pixel is given one of three categories:
* Class 1: Pixel belonging to the pet.
* Class 2: Pixel bordering the pet.
* Class 3: None of the above/a surrounding pixel.
## Model
![test_img](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png)
This deep neural network is implemented with Keras functional API, which makes it extremely easy to experiment with different interesting architectures.

Output from the network is a 128*128 which represents mask that should be learned.
## Training
The model is trained for 20 epochs.

After 20 epochs, calculated accuracy is about 0.88.

Loss function for the training is basically just a sparse categorical crossentropy.
## Architecture
![test_img](https://github.com/Sann-Htet/U-Net-Image-Segmentation/blob/master/images/U-net-architecture.png?raw=true)
Used Keras utils function called `plot_model` to generate a more visual diagram, including skip connections. The generated image generated in Colab is rotated 90 degrees so that we can see U-shaped architecture.
## Results
Use the trained model to do segmentation on test images, the result is statisfactory.
![test_image](https://github.com/Sann-Htet/U-Net-Image-Segmentation/blob/master/images/segmented_images.png?raw=true)
## Plot training history
![test_img](https://github.com/Sann-Htet/U-Net-Image-Segmentation/blob/master/images/Accuracy%20and%20loss.png?raw=true)
The learning curve during training indicates that the model is doing well on both the training dataset and validation set, which indicates the model is generalizing well without much overfitting.
