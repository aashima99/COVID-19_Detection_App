# COVID-19 DETECTION APP

COVID-19, or more commonly known as the Novel Coronavirus disease is a highly infectious disease that appeared in China towards the end of 2019. This disease is caused by SARS-CoV-2, a virus that belongs to the large family of coronaviruses. The disease first originated in Wuhan, China in December 2019 and soon became a global pandemic, spreading to more than 213 countries.
The most common symptoms of COVID-19 are fever, dry cough, and tiredness. Other symptoms that people may experience include aches, pains, or difficulty in breathing. Most of these symptoms show signs of respiratory infections and lung abnormalities which can be detected by radiologists.
Thus, it is possible to use Machine Learning algorithms to detect the disease from images of Chest X-rays and CT scans. Automated applications can be created to help support radiologists. 
This project is an attempt to use four Deep Learning algorithms, namely: VGG16, ResNet50, InceptionV3 and Xception to detect Covid-19. 

#### COVID-19 Detection based on Chest X-rays and CT Scans using four Transfer Learning algorithms: VGG16, ResNet50, InceptionV3, Xception. The models were trained for 500 epochs on around 1000 Chest X-rays and around 750 CT Scan images on Google Colab GPU. A Flask App is developed wherein user can upload Chest X-rays or CT Scans and get the output of possibility of COVID infection.

After training, the accuracies acheived for the model are as follows:
<pre>
                InceptionV3  VGG16   ResNet50   Xception
Chest X-rays    96%          94%      83%       92%

CT Scans        93%          93%      80%       95%
</pre>

## Table of Contents
1. [**WEB INTERFACE**](#web-interface)
2. [**DATASET USED**](#dataset-used)
3. [**METHODOLOGY OF THE PROJECT**](#methodology-of-the-project)
4. [**IMPLEMENTATION AND BASIC METHODOLOGY**](#implementation-and-basic-methodology)
5. [**EVALUATIONS AND RESULTS**](#evaluations-and-results)
6. [**TECHNICAL CONCEPTS AND DEEP LEARNING MODELS USED**](#technical-concepts-and-deep-learning-models-used)


## Web Interface

### Home Dashboard 
![Alt Text](/images/.png)


### Preventions
![Alt Text](/images/.png)


### FAQs
![Alt Text](/images/.png)


## DATASET USED

The dataset for the project was gathered from two sources:

1) Chest X-ray images (1000 images) were obtained from: https://github.com/ieee8023/covid-chestxray-dataset
2) CT Scan images (750 images) were obtained from: https://github.com/UCSD-AI4H/COVID-CT/tree/master/Data-split 80% of the images were used for training the models and the remaining 20% for testing.


## METHODOLOGY OF THE PROJECT 
![Alt Text](/screenshots/Methodology.PNG)


## IMPLEMENTATION AND BASIC METHODOLOGY

### Building the Model
First 3 custom layers were added to the four different pretrained models so that they can be trained on our dataset. 
The images in the dataset were of different sizes. Thus, It needed to be resized to a fixed size before they can be fed to the deep learning models for training. For example, for the ResNet model, The images were resized to a size of 224 x 224 px which is considered to be the ideal size for the ResNet50 model. Therefore, the input tensor was added of shape (224, 224 , 3) to the pretrained ResNet50 model, 3 being the number of channels.
Next, Flatten layer was added to flatten all our features and a Dropout layer to overcome overfitting. Finally, the Dense output layer was added using softmax function as the activation function. Since the first half of the model is already pretrained, the trainable attribute of the previous layers was set to False. Finally, the model was combined with the adam optimizer and using categorical crossentropy as the loss function.

### Training the Model
I first defined an Image Data Generator to train the models at modified versions of the images, such as at different angles, flips, rotations or shifts.
Next, training of the model was performed, with all the required parameters. 
I had trained the model for 500 epochs with a batch size of 32 images.

### Making Predictions
Predictions were generated by running the trained models on images of the test set. The predictions for the first 10 images of the dataset and their evaluations and results are below.

## EVALUATIONS AND RESULTS
Few important results and plots that help estimate the accuracy of the models and get insights their performance.

### Sample output of test images
![Alt Text](/screenshots/sample_chest.PNG)
![Alt Text](/screenshots/sample_ct.PNG)

### Classification Reports for Chest X-rays: VGG, InceptionV3, ResNet50, Xception
![Alt Text](/screenshots/Classification_reports.PNG)

### Confusion Matrix for Chest X-rays: VGG, InceptionV3, ResNet50, Xception
![Alt Text](/screenshots/vgg_chest_cm.PNG)
![Alt Text](/screenshots/inception_chest_cm.PNG)
![Alt Text](/screenshots/resnet_chest_cm.PNG)
![Alt Text](/screenshots/xception_chest_cm.PNG)

![Alt Text](/screenshots/Classification_reports_ctscan.PNG)

### Confusion Matrix for CT Scans: VGG, InceptionV3, ResNet50, Xception
![Alt Text](/screenshots/vgg_ct_cm.PNG)
![Alt Text](/screenshots/inception_ct_cm.PNG)
![Alt Text](/screenshots/resnet_ct_cm.PNG)
![Alt Text](/screenshots/xception_ct_cm.PNG)

### Building the Flask App
Now, I used the code created by me so far to build a Flask app by integrating particular segments of my code in certain flask functions.


## TECHNICAL CONCEPTS AND DEEP LEARNING MODELS USED

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
