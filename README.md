# Food Classifier

Download the Food-101 dataset from [Kaggle](https://www.kaggle.com/kmader/food41) and put it in this repositories main folder.  

Install Kaggle API

    pip install kaggle

Sign up for a Kaggle account and then go into account. Under API, click Create new API token. This will download a file `kaggle.json`
Put `kaggle.json` into the `.kaggle/` folder. Download the food-101 dataset using the command

    kaggle datasets download -d kmader/food41

Can also download the dataset from the original paper using the commands:

    wget http://data.vision.ee.ethz.ch/cvl/food-101.tar.gz
    tar xzvf food-101.tar.gz

However, this will not include the `h5` files that the download from Kaggle provides. 

Open and run the code in Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/benmo009/food-classifier/blob/master/food_classifier.ipynb)

We are training LeNet-5, AlexNet, and VGG-16 over this dataset and comparing the performances

LeNet-5 was originally used on the MNIST dataset, which are grayscale images, as opposed to the RGB images of the food-101 dataset. It originally takes input images of 32x32.  

AlexNet is designed to take an input image of 224x224. The training images are 256x256, and random 224x224 patches from the training images are used, so there are more training images. AlexNet was origiinally used on ImageNet, and the 256x256 images are cropped from the training set.  

VGG-16 model is implemented using the model in `keras.applications`.