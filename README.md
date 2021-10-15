# COVID-19 DETECTION APP
COVID-19 Detection based on Chest X-rays and CT Scans using four Transfer Learning algorithms: VGG16, ResNet50, InceptionV3, Xception. The models were trained for 500 epochs on around 1000 Chest X-rays and around 750 CT Scan images on Google Colab GPU. A Flask App is developed wherein user can upload Chest X-rays or CT Scans and get the output of possibility of COVID infection.

After training, the accuracies acheived for the model are as follows:
<pre>
                InceptionV3  VGG16   ResNet50   Xception
Chest X-rays    96%          94%      83%       92%

CT Scans        93%          93%      80%       95%
</pre>

## Table of Contents
1. [**WEB INTERFACE**](#web-interface)
2. [**DATASET USED**](#dataset-used)
3. [**EVALUATIONS AND RESULTS**](#evaluations-and-results)
4. [**IMPLEMENTATION AND BASIC METHODOLOGY**](#implementation-and-basic-methodology)
5. [**METHODOLOGY OF THE PROJECT**](#METHODOLOGY-OF-THE-PROJECT)
6. [**TECHNICAL CONCEPTS and DEEP LEARNING MODELS USED**](#TECHNICAL-CONCEPTS-and-DEEP-LEARNING-MODELS-USED)


## Web Interface

#### Home Dashboard 
![Alt Text](/images/.png)


#### Preventions
![Alt Text](/images/.png)


#### FAQs
![Alt Text](/images/.png)


## DATASET USED

The dataset for the project was gathered from two sources:

1) Chest X-ray images (1000 images) were obtained from: https://github.com/ieee8023/covid-chestxray-dataset
2) CT Scan images (750 images) were obtained from: https://github.com/UCSD-AI4H/COVID-CT/tree/master/Data-split 80% of the images were used for training the models and the remaining 20% for testing.

## EVALUATIONS AND RESULTS
### Sample output of test images

### Classification Reports for Chest X-rays: VGG, InceptionV3, ResNet50, Xception

### Confusion Matrix for Chest X-rays: VGG, InceptionV3, ResNet50, Xception

### Classification Reports for CT Scans: VGG, InceptionV3, ResNet50, Xception

### Confusion Matrix for CT Scans: VGG, InceptionV3, ResNet50, Xception



## IMPLEMENTATION AND BASIC METHODOLOGY

## METHODOLOGY OF THE PROJECT 

### TECHNICAL CONCEPTS and DEEP LEARNING MODELS USED

#### ImageNet 
ImageNet is formally a project aimed at (manually) labeling and categorizing images into almost 22,000 separate object categories for the purpose of computer vision research.

#### ResNet50 
ResNet-50 is a convolutional neural network that is 50 layers deep. You can load a pretrained version of the network trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. Unlike traditional sequential network architectures such as AlexNet, OverFeat, and VGG, ResNet is instead a form of “exotic architecture” that relies on micro-architecture modules.

#### VGG16
VGG16 is a convolutional neural network model proposed by K. Simonyan and A. Zisserman from the University of Oxford in the paper “Very Deep Convolutional Networks for Large-Scale Image Recognition”. The model achieves 92.7% top-5 test accuracy in ImageNet, which is a dataset of over 14 million images belonging to 1000 classes.

#### Inception-V3
Inception-V3 is a convolutional neural network that is 48 layers deep. You can load a pretrained version of the network trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. As a result, the network has learned rich feature representations for a wide range of images. The network has an image input size of 299-by-299.

#### Xception
Xception is a convolutional neural network that is 71 layers deep. You can load a pretrained version of the network trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. As a result, the network has learned rich feature representations for a wide range of images. The network has an image input size of 299-by-299.

#### Flask 
Flask, issued in mid-2010 and developed by Armin Ronacher, is a robust web framework for Python. Flask provides libraries and tools to build primarily simple and small web applications with one or two functions (Das., 2017). 

#### Bootstrap 
Bootstrap is an open-source JavaScript and CSS framework that can be used as a basis to develop web applications. Bootstrap has a collection of CSS classes that can be directly used to create effects and actions for web elements. Twitter’s team developed it in 2011 (“Introduction”, n.d.).
