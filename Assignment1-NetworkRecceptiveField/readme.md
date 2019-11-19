# Network Performance on mnistTest Data
score = model.evaluate(X_test, Y_test, verbose=0)
print(score)
[0.029627236612748128, 0.9904]

# Deep Learning Building Blocks

## What is Convolution?

A convolution is an operation that changes a function into something else. We do convolutions so that we can transform the original function into a form to get more information.Here, the original image is the one on the left and the matrix of numbers in the middle is the convolutional matrix or filter.

A convolution operation is an element wise matrix multiplication operation. Where one of the matrices is the image, and the other is the filter or kernel that turns the image into something else. The output of this is the final convoluted image.

![conv](https://saama-dbe0.kxcdn.com/wp-content/uploads/2017/12/01.jpg?iv=95)

It is heart of image processing and is a mathematical operation to extract information from input. The kernel is slided over the image as part of convolution process to extract information about input and this feature map is produced.
## Filters/Kernels

Filter/Kernel is a matrix of some values with defined filter size. Expectation is that weights (or values) in the convolution filter multiplied with corresponding input image pixels will gives us a value that best represents those image pixels and thus will help us to extract key features from the input image. Filter size is one of the hyper-parameters and our choice varies between higher and smaller values. 
From CNN perspective, Kernel=Filter=Feature Extractor.
### Different type of Filters

**Blurring images**

![filter](https://saama-dbe0.kxcdn.com/wp-content/uploads/2017/12/03.png?iv=95)

**Sobel Filters for Edge Detection**

![sobel](https://saama-dbe0.kxcdn.com/wp-content/uploads/2017/12/05.jpg?iv=95)

In CNNs, filters are not defined. The value of each filter is learned during the training process. By being able to learn the values of different filters, CNNs can find more meaning from images that humans and human designed filters might not be able to find.

## Epochs

An Epoch is when an full training dataset is passed forward through the Neural Network and backward through the neural network only 

We always train our Neural Network for more than one epoch because network weights and learning rates needs can't be optimized through backpropagation and gradient descent with only one iteration of dataset. Generally one epoch tend to make model underfitting. No of epoch is another hyper-parameter which needs to be monitored with validation set accuracy, training accuracy. High number of epoch will make model more familiarized with training set and will not allow to be generalized. We stop training the network when we don't see any improvement of validation accuracy or model is getting towards overfitting or there is slight improvement of accuracy. Passing through one epoch cost computation power which involves money and time. So no of epoch is very important hyper-parameter. Dataset nature and diversity also impacts no of Epoch to be used for a model to get trained and generalized. Batch size and Epoch are quite inter-dependent for network optimization.

![EpochVsAccuracy](https://github.com/amitkayal/akDeepLearningMaster/blob/master/Training-error-versus-epoch-number-for-the-neural-network-model.png?raw=true)


