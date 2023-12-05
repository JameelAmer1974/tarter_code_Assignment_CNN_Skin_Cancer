# CNN Skin Cancer Project 
> Problem statement: To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.


## Table of Contents
* [Dataset](#Dataset)
* [Project Pipeline](#Project-Pipeline)
* [Model 1](#Model_1)
* [Model 2](#Model_2)
* [Model 3](#Model_3)

<!-- You can include any other section that is pertinent to your problem -->

## Dataset
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.

The data set contains the following diseases:

- Actinic keratosis
- Basal cell carcinoma
- Dermatofibroma
- Melanoma
- Nevus
- Pigmented benign keratosis
- Seborrheic keratosis
- Squamous cell carcinoma
- Vascular lesion 


## Project Pipeline
Data Reading/Data Understanding:
- Defining the path for train and test images 
Dataset Creation:
- Create train & validation dataset from the train directory with a batch size of 32. Also, make sure you resize your images to 180*180.
Dataset visualization:
- Create a code to visualize one instance of all the nine classes present in the dataset 
Model Building & training: 
- Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
- Choose an appropriate optimizer and loss function for model training
- Train the model for ~20 epochs
- Write your findings after the model fit. You must check if there is any evidence of model overfit or underfit.
Chose an appropriate data augmentation strategy to resolve underfitting/overfitting 
Model Building & training on the augmented data :
- Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
- Choose an appropriate optimizer and loss function for model training
- Train the model for ~20 epochs
- Write your findings after the model fit, and see if the earlier issue is resolved or not.
Class distribution: Examine the current class distribution in the training dataset 
- Which class has the least number of samples?
- Which classes dominate the data in terms of the proportionate number of samples?
Handling class imbalances:
- Rectify class imbalances present in the training dataset with the Augmentor library.
Model Building & training on the rectified class imbalance data:
- Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
- Choose an appropriate optimizer and loss function for model training
- Train the model for ~30 epochs
- Write your findings after the model fit, and see if the issues are resolved or not.

<!-- As the libraries versions keep on changing, it is recommended to mention the version of the library used in this project -->

## Model 1
CNN model, which can accurately detect 9 classes present in the dataset. Use layers. experimental.
preprocessing.Rescaling to normalize pixel values between (0,1). The RGB channel values are in the [0, 255] range. 
This is not ideal for a neural network. Here, it is good to standardize values to be in the [0, 1]
the model design:
- Input 180*180*3
- Convolution 1 16 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Convolution 1 32 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Convolution 1 64 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Flatten Layer
- Dense Layer 128 Units
- Dense Layer 9 Units
- Output layer 9 Units

![CNN](https://github.com/JameelAmer1974/tarter_code_Assignment_CNN_Skin_Cancer/assets/142296713/8dae7d5a-3eb2-490a-a6ae-c57b76dd13ec)


The output
- The model is Overfitting
- Training Accuracy ~ 87%
- Validation Accuracy ~ 40%
- since the training accuracy is 87% and the validation accuracy 40% it's clear that the module is overfitting

To fix this issue we will add a new augmentation layer to
- Random Rotation
- Random Zooming
- Random Flipping




## Model 2
 use Dropout layer to manage the overfitting
 
the model design:
- Input 180*180*3
- Convolution 1 32 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Convolution 1 64 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Dropout 0.3
- Convolution 1 128 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Dropout 0.3
- Flatten Layer
- Dense Layer 128 Units
- Dropout 0.3
- Dense Layer 9 Units
- Output layer 9 Units

![CNN1](https://github.com/JameelAmer1974/tarter_code_Assignment_CNN_Skin_Cancer/assets/142296713/dd102301-7dbd-400a-91f5-bc27375466e6)

 
 The output
- The model is Underfiting
- Training Accuracy ~ 62%
- Validation Accuracy ~ 40%
- The gap between training and testing accuracy has decreased but the overall accuracy of the model did not improve.


## Model 3
- define the classes 
- add more samples for each class (500 sample)
 
the model design:
- Input 180*180*3
- Convolution 1 16 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Convolution 1 32 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Convolution 1 64 3*3 filter
- ReLU Activation
- Max Pooling 2*2 filter
- Dropout 0.2
- Flatten Layer
- Dense Layer 128 Units
- Dense Layer 9 Units
- Output layer 9 Units
  
![CNN2](https://github.com/JameelAmer1974/tarter_code_Assignment_CNN_Skin_Cancer/assets/142296713/6f60bec1-abe0-43f7-a305-eda43db6f6e8)

The output
- We can use this model as a final model
- Training Accuracy: ~88%
- Validation  Accuracy: ~85% 

## Contact
Created by Jameel Amer [jamer@SmartSoft-co.com] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
