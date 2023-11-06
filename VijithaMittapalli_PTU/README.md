Student Name - Vijitha Mittapalli
Department & Year - CSE 4th year
College Name - Puducherry Technological University
Email - vijithamittapalli2003@gmail.com





# Dog Breed Classification using InceptionV3 CNN Model on Stanford Dogs Dataset
## Description
The <a href= "http://vision.stanford.edu/aditya86/ImageNetDogs/">Stanford Dogs Dataset</a> contains images of 120 breeds of dogs from around the world. This dataset has been built using images and annotation from ImageNet for the task of fine-grained image categorization. It was originally collected for fine-grain image categorization, a challenging problem as certain dog breeds have near identical features or differ in colour and age.

I have used the InceptionV3 CNN Model, which is pre-trained on the ImageNet dataset for classification. Data augementation has been used for making the model generalize better and also to avoid overfitting. The model achieved an accuracy of 85% on validation set, which is decent for this dataset.



### Pre-Requisites
Required tech stack:

- NumPy
- Pandas
- Scikit-image
- IPython
- Matplotlib
- Tensorflow 2.X
- Keras


## Dataset
Contents of the dataset:
- Number of categories: 120
- Number of images: 20,580
- Annotations: Class labels, Bounding boxes

The dataset can be downloaded from <a href= "http://vision.stanford.edu/aditya86/ImageNetDogs/">here.</a>

Sample images of 50 different categories from the dataset:

![Images of Dogs](/images/dogs_images.jpeg)

## Approach
### Data Augmentation
Data augmentation is done through the following techniques:
- Rescaling (1./255)
- Shear Transformation (0.2)
- Zoom (0.2)
- Horizontal Flipping
- Rotation (20)
- Width Shifting (0.2)
- Height Shifting (0.2)

![Augmented Image](/images/augmented_image.png)

### Model Details
```
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
inception_v3 (Functional)    (None, 5, 5, 2048)        21802784  
_________________________________________________________________
global_average_pooling2d (Gl (None, 2048)              0         
_________________________________________________________________
dropout (Dropout)            (None, 2048)              0         
_________________________________________________________________
dense (Dense)                (None, 120)               245880    
=================================================================
Total params: 22,048,664
Trainable params: 245,880
Non-trainable params: 21,802,784
_________________________________________________________________
```
A detailed layout of the model is available [here.](/images/model_plot.png)

### Training Results
![Model Accuracy and Loss](/images/train_acc_loss.png)

The `training_csv.log` file contains epoch wise training details.

### What I Learned from this Assessment
 I worked with the pre-trained InceptionV3 model for image classification and got to learn about the benifits of transfer learning, which allows us to 'transfer' the weights of low-level features that are inherent in most images and apply it to the initial layer of our CNN.

