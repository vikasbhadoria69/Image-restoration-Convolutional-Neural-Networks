# Image restoration by using Convolutional Neural Networks
* Used different techniques for adding noise to the image and using OpenCV library to reduce the brightness so as to create a perfect dataset of distorted images.
* Used the vgg19 CNN model as a part of transfer learning technique to see how effective CNN is to extract the original content from a distorted image.
* Built my own CNN model and trained it on a huge dataset to efficiently restore distorted images.

## Code and Resources Used
**Python Version:** 3.7  
**Packages:** pandas, numpy, OpenCV, matplotlib, vgg19, TransferLearning, Keras. 

## Dataset
The image dataset consists of 8,750 images and most of the images I have scrapped from the
internet. The dataset also consists of pictures from personal life of my friend who is an aspiring photographer. All these images are
then resized to 500x500 before using in the model.

## Image enhancement
Image enhancement is the way toward altering computerized images with the goal that the
outcomes are more reasonable for show or further image investigation. Image enhancement
should be possible by evacuating noise, image sharpening, or lighting up an image, making it
less demanding to distinguish the key highlights. Image enhancement algorithms include
deblurring, filtering, and contrast methods. Deep learning utilizes neural systems to find out
helpful portrayals of highlights straightforwardly from image information. Neural systems
are pre trained to distinguish and remove different sorts of disruption from images and
improve the images.

## Methodology
##### The project work was divided into the following 4 phases

### Phase 1:
In order to test the theory there has to be a dataset which consists of clear images
and the corresponding distorted images. The idea is to use supervised learning techniques to
train the model and for that the real images will act as labels. In order to create artificial
corresponding distorted images, noise has been added to the real images and then by using
the OpenCV library brightness of images are reduced.
The noise added here is “Salt & Pepper” noise as different approaches were tried along with
gaussian noise, poisson noise, speckle but the best results were with “Salt & Pepper”.
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/Rangoli1.png)![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/Rangoli_noise.png)

- ***Issues with Phase 1: NO***

### Phase 2: 
In phase 2 ‘transfer learning’ technique has been used as a part of research to
observe the effects of CNN for image restoration. The award winning VGG19 neural model
has been used. This model consists of 16 convolutional layers and 3 fully connected layers
hence the name Vgg19. The pre-trained parameters of this model are kept constant and only
the feature extraction part of the model has been used for this project’s phase 2.
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/Rangoli_vgg19.png)
The output of this phase shows how powerful CNN can be to restore images with noise and
captured in low light intensity. The results motivates me to build a CNN and train it to
output such restored images when a noisy image is fed as an input.
- ***Issues with Phase 2: NO***

### Phase 3: 
In phase 3 the idea is to build a CNN model which can be trained on my dataset
consisting of real and noisy images. The basic concept behind this training will be the same
as in phase 2. The model will be provided with real images as labels and noisy images which
will be altered as the model performs gradient descent to minimize the error.
The model built in this phase for training is a 16 layer CNN which can be used for feature
extraction of the images. This model is built using inspiration from ResNet model
architecture, google’s teachable machine CNN model’s architecture and Vgg19’s architecture.
The architecture and the idea behind all these models were carefully studied and then
implemented to build this model.
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/model1.png)
The model is then trained on my dataset. For training the model the optimizer used is
‘Adam’, loss function used is ‘Mean Squared Error’, activation function used is ‘Relu’. Since
training with images is quite memory expensive, the model is trained in Google Colab which
provides free GPU service to train such intensive models.
- ***Issues with Phase 3: NO***

### Phase 4:
In this phase the model built and trained is put to test on noisy low light images
which it has never seen before. The test images go through the same process of artificial
noise addition and brightness reduction. This time only the noisy image will be an input to
the model without any labels. The prediction of the model can be seen below.
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/output1.png)
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/op2.png)
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/op3.png)
![alt text](https://github.com/vikasbhadoria69/Image-restoration-Convolutional-Neural-Networks/blob/master/Output%20images/op4.png)
- ***Issues with Phase 4: The model is producing inappropriate results in case of enhancing a very bright section of an image.***

## Conclusions
In this project in order to meet the intended objectives I first created a dataset with real
images, noise was then added artificially to the images. After trying out different types of
noise I found “Salt & Pepper” more appropriate. Vgg19 model was then used to observe the
effects of CNN for image restoration and enhancement and the results were very
encouraging. In phase 3 I then built my own model by taking inspirations from architecture
of other award winning models. I then trained the model on my dataset in google colab. The
predictions of the model are very encouraging and can be improved further. The overall
results can be concluded in 3 points:
1. ***The model works pretty good with low light images.***
2. ***The noise used is ‘Salt and Pepper’ to train the model with a realistic low light image
although it is not tested for other type of noises.***
3. ***The model is producing inappropriate results in case of enhancing a very bright section of
an image. The reason might be due to presence of salt pepper noise and might produce
better results in case of real-time low light image.***


**The entire project report is uploaded above as a pdf _Image_Restoration_CNN_Project_ kindly go through the PDF if a detailed information about the project is needed**
### Thank you.

