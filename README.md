# pclubsecytaskML
The program aims to achieve digit recognition using ML techniques.
Convolutional Neural Network model has been used to implement it.
For now, it has been trained using mnsit dataset of 28x28 images of digits 0-9.
For testing and training the dataset has been divided, a function to take external images is implemented, but it has to be done directly in the code, i have not yet made a convinient interface for that.

The Code mainly divides into two segments:
Implementing CNN
Training and test model

![WhatsApp Image 2022-08-17 at 1 52 14 AM](https://user-images.githubusercontent.com/96115625/184978162-0c53715c-f281-4a30-9cc8-ec91f934e27f.jpeg)

Implementation of CNN::
Three classes have been used::
Convulation operation
Maxpool
Softmax


Convulation operation::
constructor---Generates nf normalised filters randomised via normal distribution function. 
patches--Generates patches from image with same dimension of the filter which covers the whole image part by part.
fwd_prop-- multiplication of filter and patch
back_prop-- takes input from maxpool layer and updates the weights of filter by subtracting [learningrate * maxpool_data * patch] for nf filters.


Maxpool layer::
