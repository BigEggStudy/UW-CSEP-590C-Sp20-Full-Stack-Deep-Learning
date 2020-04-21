# Assignment 3: Convnets

## Q1 Receptive Field
What is the receptive field (in number of pixels of the original image) of three stacked 3x3 conv filters with stride 1x1? Write your answer in the “3x3” format exactly.

> It is a 7x7 conv filters.

## Q2 Convnet Math
The input to a conv layer is a 100x100x3 image. The filter size is 5x5 with a 5x5 stride and 'VALID' padding, and there are 128 filters. What is the output volume? Write your answer in the “100x100x3” format exactly.

> **Flatten:** 5 (height) * 5 (width) * 3 (depth) = 125 dimensional
>
> **Im2Col:** X_col = 125 * 400 (number of filters can fit in the image)
>
> W_row = 128 * 125
>
> W @ X [128 * 400]
>
> Reshape to 20x20x128
>
> So, the output should be 20x20x128

## Q3 ResBlock
A “residual block” is the foundational unit of the ResNet convolutional architecture. The diagram below shows how it works. Explain why this innovation allowed successful training of deeper-than-ever networks.

![ResBlock](https://s3-us-west-2.amazonaws.com/gradescope-static-assets/fsdl/resblock.png)

> I think there have 2 major problems that before residual block comes out.
>
> 1. When choose ReLU as the activation function, there have one drawback that: because the outputs of this function are zero for input values that are below zero, the neurons of the network can be very fragile during training and can even “die”. Which means during the weight updates the weights are adjusted in such a way that for certain neurons the inputs are always below zero. And those neurons are always zero and do not contribute to the training process.
>
> 2. When we have a deep networks, the gradient tends to vanish. This is because the weights are small numbers, and each time the input goes through a layer, it will get small via multiply the weights. And this can let the signal become very small numbers in the later layers. Also this will cause the gradient become even smaller, even doesn't have any affect in the weights update, which known as Vanishing Gradient Problem.
>
> With the residual block, the later layers can always get the input before and get more information to learn.

## Q4 InceptionNet
What purpose do 1x1 convolutions serve in the InceptionNet block?

![InceptionNet](https://s3-us-west-2.amazonaws.com/gradescope-static-assets/fsdl/inception.png)

> The 1x1 convolutions is used to reduce the number of channels in the inputs. Because
>
> * The 1×1 filter can be used to create a linear projection of a stack of feature maps.
>
> * The projection created by a 1×1 can act like channel-wise pooling and be used for dimensionality reduction.
>
> * The projection created by a 1×1 can also be used directly or be used to increase the number of feature maps in a model.
>
> Reference: https://machinelearningmastery.com/introduction-to-1x1-convolutions-to-reduce-the-complexity-of-convolutional-neural-networks/

## Q5 Object Detection
For a project, you have to detect all cars in images coming from a webcam, in real time. The resolution is reasonable (let's say 1080p). The framerate is 5 frames per second. You have access to a GPU on the detection computer. How would you go about doing this? It's more than acceptable to use existing software. Feel free to research on the internet.

>
