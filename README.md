# ResNet-for-MNIST-
Multiclass classification of handwritten datasets using ResNet (Residual Neural Network) architecture.
ResNet, short for Residual Network is a specific type of neural network that was introduced in 2015 by Kaiming He, Xiangyu Zhang, Shaoqing Ren and Jian Sun in their paper “Deep Residual Learning for Image Recognition”.
Mostly in order to solve a complex problem, we stack some additional layers in the Deep Neural Networks which results in improved accuracy and performance. The intuition behind adding more layers is that these layers progressively learn more complex features. For example, in case of recognising images, the first layer may learn to detect edges, the second layer may learn to identify textures and similarly the third layer can learn to detect objects and so on. But it has been found that there is a maximum threshold for depth with the traditional Convolutional neural network model. Here is a plot that describes error% on training and testing data for a 20 layer Network and 56 layers Network.
## Residual Block
This problem of training very deep networks has been alleviated with the introduction of ResNet or residual networks and these Resnets are made up from Residual Blocks.

![image](https://user-images.githubusercontent.com/67157901/142720231-d1a6f972-5e8f-4842-a60b-144810ad4a88.png)
The very first thing we notice to be different is that there is a direct connection which skips some layers(may vary in different models) in between. This connection is called ’skip connection’ and is the core of residual blocks. Due to this skip connection, the output of the layer is not the same now. Without using this skip connection, the input ‘x’ gets multiplied by the weights of the layer followed by adding a bias term.

Next, this term goes through the activation function, f() and we get our output as H(x).

H(x)=f( wx + b ) 
or H(x)=f(x)
Now with the introduction of skip connection, the output is changed to

H(x)=f(x)+x
There appears to be a slight problem with this approach when the dimensions of the input vary from that of the output which can happen with convolutional and pooling layers. In this case, when dimensions of f(x) are different from x, we can take two approaches:

The skip connection is padded with extra zero entries to increase its dimensions.
The projection method is used to match the dimension which is done by adding 1×1 convolutional layers to input. In such a case, the output is:
H(x)=f(x)+w1.x
Here we add an additional parameter w1 whereas no additional parameter is added when using the first approach.
