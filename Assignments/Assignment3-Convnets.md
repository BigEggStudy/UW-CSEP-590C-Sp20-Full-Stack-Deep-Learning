# Assignment 3: Convnets

## Q1 Receptive Field
What is the receptive field (in number of pixels of the original image) of three stacked 3x3 conv filters with stride 1x1? Write your answer in the “3x3” format exactly.

## Q2 Convnet Math
The input to a conv layer is a 100x100x3 image. The filter size is 5x5 with a 5x5 stride and 'VALID' padding, and there are 128 filters. What is the output volume? Write your answer in the “100x100x3” format exactly.

## Q3 ResBlock
A “residual block” is the foundational unit of the ResNet convolutional architecture. The diagram below shows how it works. Explain why this innovation allowed successful training of deeper-than-ever networks.

![ResBlock](https://s3-us-west-2.amazonaws.com/gradescope-static-assets/fsdl/resblock.png)

## Q4 InceptionNet
What purpose do 1x1 convolutions serve in the InceptionNet block?

![InceptionNet](https://s3-us-west-2.amazonaws.com/gradescope-static-assets/fsdl/inception.png)

## Q5 Object Detection
For a project, you have to detect all cars in images coming from a webcam, in real time. The resolution is reasonable (let's say 1080p). The framerate is 5 frames per second. You have access to a GPU on the detection computer. How would you go about doing this? It's more than acceptable to use existing software. Feel free to research on the internet.
