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
back_prop-- takes input from maxpool layer and updates the weights of filter by subtracting [learningrate * maxpool_data * patch] for nf filters, return the parameters.


Maxpool layer::
patches--- generates new patches of original size/filter size, tbe patch generrator iterates over the matrix by filter_size rather than one block at a time.
fwd_prop--- iterates over the generates patches while storing the max in the patch in an output matrix.
back_prop--- gives the array of orignial size, divides in patches, filled with zero except the max element in the patch
 NOTE:: there are no weights/biases involved in this layer, hence no update is being done, it simply plays with max value in patches of the image.
 
Softmax layer::
Constructor---initiialzes the weights and biases.
Fwd_prop--- first we flatten the 3D array to 2D, calculate [wX+b], to get a single output vector. Further it is transformed to prababilistic output using exponential. (Softmax Transfer)
Back_prop--- returns input for maxpool unit, which further propogates to convulation operation.



