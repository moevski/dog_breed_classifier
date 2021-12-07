[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Keras Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"

# Building a Dog Identification App using CNN

## Table of Contents

1. [Project Overview](#overview)
2. [Project Instructions](#proj_inst)
3. [File Descriptions](#file_desc)
4. [Summary](#summary)
5. [Link to MY Full Blog Post](#blog)
6. [Acknowledgements](#ack)


## Project Overview<a name="overview"></a>


This is about how to build an Identification App to detect the presence of a human face or a dog in an image, then classify the dog breed using Convolutional Neural Network (CNN) in case a dog is detected or suggest the most dog breed that resembles the human face in case human face is detected.

The strategy to tackle this problem is summarized in four steps:

- Identify presence of human face in an image
- Identify the presence of a dog in an image
- Classify a dog breed for dogs or suggest a dog breed that resembles the human face
- Build the algorithm


![Sample Output][image1]



## Project Instructions<a name="proj_inst"></a>

1. Clone the repository and navigate to the downloaded folder.
```	
git clone https://github.com/moevski/dog_breed_classifier
cd dog-project
```

2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 

3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 

4. Donwload the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.

5. Install Conda [link](https://www.anaconda.com/products/individual) and open the notebook, all imported packages are included in conda distribution

```
jupyter notebook dog_app.ipynb
```


## File Descriptions<a name="file_desc"></a>
Main files used are as follows:

	- README.md: This file
	- dog_app.ipynb: Jupyter notebook that includes full details
	- dog_app.html: html version of the Jupyter notebook
	- extract_bottleneck_features.py: python script to extract bottleneck features
	- \haarcascades
			- haarcascade_frontalface_alt.xml: a pre-trained face detector provided by OpenCV
	- \saved_models
			- weights.best.inception_v3.hdf5: saved InceptionV3 model weights
			- weights.best.ResNet50.hdf5: saved ResNet50 model weights
	- \test_images: contains various test images used by the algorithm


## Summary<a name="summary"></a>

This Project described an algorithm that detect 2 objects, human faces and dogs, in case a dog is detected it classify it’s breed, in case it’s human it classify the most resembling dog breed for the detected human face.
Human face detector was build based on pre-trained Haarcascades feature-based cascade classifiers OpenCV model, dog detector was based on pre-trained ResNet50 CNN pre-trained model, and finally image classifier was based on InceptionV3 CNN model, I also tried to build a simple custom model as a base line. the result from the simple custom model was 4.5% accuracy which is not that bad considering the complexity of the problem and simplicity of network architecture, however, this increase to over 81% using InceptionV3 model.


## Link to MY Full Blog Post<a name="blog"></a>

[Full Blog Post](https://moevski.medium.com/building-a-dog-identification-app-using-cnn-5c33d25d1a1f)

## Acknowledgements<a name="ack"></a>
the starter Jupyter notebook and data images used were provided by Udacity as part of Data Scientist ND
