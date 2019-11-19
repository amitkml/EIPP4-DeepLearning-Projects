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
### Filter size design

Following factors plays key role in determining filter/kernel size.

- Smaller filter look at few pixels at a time and hence has smaller receptive field per layer while bigger filter look at higher no of pixels at a time so they provide bigger receptive field per layer.
- Smaller filter will help us to extract highly local features(smaller and complex ones) and may not have general overview of the input while bigger filter will help us to get basic component of the image as they have higher receptive field.
- Smaller filters helps us to extract higher no of information as the output size of feature map gets reduced slightly(Ex: Input size is 400X400 and after 3x3 convolution the feature map becomes 398x398) and these information can be used later in the network. Higher filter size results in much smaller feature map size and so amount if information gets reduced.
- Lower size kernel has lower number of weights which makes convolution process computationally efficient which this is exactly opposite for higher size kernel.
- Lower size kernel often results in higher number of layers into network and this means network needs to store all the layer details into memory for backpropagation which results in requirement of higher memory. Higher filter uses less storage memory for backpropagation.

Reducing the kernel size seems to be trend and 3x3 is most popular filter nowadays.

- Year-2012, Alex Net used 11x11 filter size
- Year-2013, ZFNet used 7x7 filter size
- Year-2014, GoogleNet used 7x7(first few layers) and 5x5
- Year 2014, VGG used 3x3 filter size

## 1x1 Filter
This acts like a DJ who does mix and match. This type of filter helps us to maintain special dimension aspect with channel reduction. Extensively used in GoogLeNet architecture as **"bottleneck layer"**. So this helps basically projecting depth down.

We could have used 3x3 filter with lower number of channels but that does not help us to maintain spatial dimensions.

![1x1](https://github.com/amitkayal/akDeepLearningMaster/blob/master/1x1.gif?raw=true)

![1x1](https://github.com/amitkayal/akDeepLearningMaster/blob/master/1x1_Convolution.JPG?raw=true)



## Epochs

An Epoch is when an full training dataset is passed forward through the Neural Network and backward through the neural network only 

We always train our Neural Network for more than one epoch because network weights and learning rates needs can't be optimized through backpropagation and gradient descent with only one iteration of dataset. Generally one epoch tend to make model underfitting. No of epoch is another hyper-parameter which needs to be monitored with validation set accuracy, training accuracy. High number of epoch will make model more familiarized with training set and will not allow to be generalized. We stop training the network when we don't see any improvement of validation accuracy or model is getting towards overfitting or there is slight improvement of accuracy. Passing through one epoch cost computation power which involves money and time. So no of epoch is very important hyper-parameter. Dataset nature and diversity also impacts no of Epoch to be used for a model to get trained and generalized. Batch size and Epoch are quite inter-dependent for network optimization.

![EpochVsAccuracy](https://github.com/amitkayal/akDeepLearningMaster/blob/master/Training-error-versus-epoch-number-for-the-neural-network-model.png?raw=true)

## 3X3 convolution filter
3X3 convolution filter, in general will always have a third dimension in size and this is the most eficient fielter in today's world. So it will have 9 weights and they will be learnt as part of backpropagation. Initial value can be set by keras inbuilt function of kernel initializer.
One of the commercial reason for using 3x3 filter is that our current GPU's(NVDIA, Intel etc) are optimized heavily for such filter. Also note that, all kernel are of Odd size and we generally don't use even size kernel. This is because am even number does not have concept of mirror and so we can't talk of things are in right and things are in left.

It is always number of parameters which are less with 3x3 filter. Any filter like 5x5 or 7x7 can be represented by a number of 3x3. Lets see how? 

**Scenario:  One(Channel=1) 5x5 filter**

- Input Size: 5x5 
- Output size: 1x1
- No of parameters: 25

**Scenario: One(Channel=1) 3x3 filter**

- Input Size: 5x5 
- Output after 1st convolution: 3x3
- Output after 2nd convolution: 1x1
- Final Output: 1x1
- No of parameters=18

Above example shows how a 5x5 filter can be represented by 2 no of 3x3 filter and also it reduces no parameters to be learning. But here no of convolution operation is twice. The receptive field of the 5x5 kernel can be covered by two 3x3 kernels.  Stacking small filters gives us more discriminative power via the non-linearity and via the composition of abstraction. 

## Activation Functions

One of the problem with unstructured data (Video, Audio, Text, Images etc) is that linear separation does not work and activation function helps us to bring non-linearity aspect into the Neural network architecture. Output of NN will be a simple linear function if we don't apply an activation function and so it would not be able to resolve any complex problem. We can assume a NN as simple regression model without activation function.

NN is considered as universal function approximations and hence NN should be able to learn from any input or map any sort of input with their output. So this means our NN which makes output as f(X) with non-linearity introduced by activation function will be able to map/learn. Activation function also helps us to have **differentiable** and this helps us with backpropagation with Gradient descent. Any differentiable function will have derivative and hence will help to back propagate the loss and correct weights. So NN with activation function helps us to achieve **Input times weights , add Bias and Activate**.

Most popular activation functions are

- ReLU - Rectified Linear Unit
- Sigmoid/Logistic

**ReLU - Rectified Linear Unit**

This activation unction basically means **R(x) = max(0,x) i.e if x < 0 , R(x) = 0 and if x >= 0 , R(x) = x**. This is very easy approach to introduce non-linearity and helps us to have differentiable which helps to resoolve vanishing gradient function. This is most popular activation function and almost all CNN layers uses this.

Only **limitation** with this activation function is that it can be used **<u>only in hidden layers of Neural Network Models</u>**. 

![ReLU](https://github.com/amitkayal/akDeepLearningMaster/blob/master/ReLU%20Activation%20Function.JPG?raw=true)



**Sigmoid/Logistic**

It is an activation function of form `f(x) = 1 / 1 + exp(-x)` . Its Range is between 0 and 1. It is a S — shaped curve. It is easy to apply and helps us to tackle vanishing gradient function. Problem with Sigmoid are that it has slow convergence, output not zero centered and gradient saturation near the top and below. This is where ReLU is in better position to handle.

![Sigmoid](https://github.com/amitkayal/akDeepLearningMaster/blob/master/Sigmoid%20Activation%20Function.JPG?raw=true)

## Receptive field and its Importance

Refer the following diagram where the output in the 2nd layer (marked in green) covers 5x5 pixel of input image and so this is its effective receptive field (RF).  Its local receptive field will be 3x3. Local RF is relative to its previous layer and Effective RF is w.r.t original input image to the network. Similarly each cell (marked in light yellow) covers 3x3 of the input image and so its Local RF is 3x3.  **RF is actually the amount of context that a neuron sees in the input to predict its output**. RF is important because our last layer need to see atleast full image to predict. So this means we need to add layers/follow the process described below to reach the object size or as close as we can of object size.
#### How to increase Receptive field?

The three ways in which we can increase the RF are:

1. Make larger kernel sizes

2. Use higher stride or pooling

   **Example conv1D with 2 layers, kernel size 3 and stride 2**

![RF](https://cdn-images-1.medium.com/max/900/1*dMqIw023uH21yu1L8UpJcw.png)

Lets analyze following two image and understand more easily how we can build the network and ensure last layer of network can see the whole image.  **We can see the whole pyramid base from top for both the image but later one has steps and hence that involves no of layers less. This means instead of stacking more layers to increase ERF, it is better to do step wise whereby we can still increase ERF and reduce no of parameters. This step aspect can be achieved by increasing stride or introducing max pooling**.

![Egyptian](https://www.history.com/.image/t_share/MTU3ODc3NjU1NjcyMTM3MDMz/egyptian-pyramids.jpg) and ![mylan](https://mymodernmet.com/wp/wp-content/uploads/2018/11/egyptian-pyramids-2.jpg)

3. Using dilation factors in the kernels
