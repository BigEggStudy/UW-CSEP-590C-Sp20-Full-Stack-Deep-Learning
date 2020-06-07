# Final Exam

## Q1 Weight Initialization
Is it a good idea to initialize the weight matrix of a neural network layer with all zeros?

> No, It will perform very poorly, because the neurons will learn the same features during training.

## Q2 Data Normalization
What is a reason to normalize input data to a neural network? How can it be done?

> The reasons are:
> 1. Any rescaling of an input vector can be effectively undone by changing the corresponding weights and biases, and can still have the same outputs.
> 2. With the normalize, the training will faster to reach the global minima.
> 3. The sigmoid function had been use lesser as an activation function, because tanh function will have better performance. And normalization can let both positive and negative values used as inputs which makes learning more flexible (faster)
>
> The way to normalize the data are:
> 1. Normalization (Min-Max Scalar)
> 2. Robust Scalar (Scaling to median and quantiles)
> 3. Standardization (Gaussian distribution)

## Q3 Convolutional Neural Networks
Describe in your own words the purpose of using convolutional layers in neural networks.

> We use convolution layer is to extract the features, like in image, convolution layer can learn to detect the edge, mast and other interesting stuffs. ANd it can use fewer weights because they are shared.

## Q4 Transformer vs LSTM
For a sequence-to-sequence problem such as machine translation, describe a couple of pros and cons of using an LSTM-based vs a Transformer-based approach.

> Pros for Transformer:
> * It's not sequential, so no need to process word by word, and support parallelize the training
> * Support self attention
> * Can support positional embeddings
> * Have better performance on long dependency because it process a sentence as a whole
>
> Pros for LSTM:
> * Have much lesser parameters
> * It can retained the past information through past hidden states

## Q5 GPUs
What are at least three advantages of using the 2080 Ti GPU vs the 1080 Ti GPU for deep learning?

> * Similar price for new one
> * Higher performance (1.3x faster in 32bit and 2x faster in 16bit)
> * Newer Architecture
> * Support 16bits
> * Support Tensor TFlops

## Q6 Sequence problem
Give an example of a many-to-one sequence problem

> A many-to-one problem can be high-frequency financial volatility forecasting, that the input should be a stream of quotes and trades over last few minutes and output the prediction (up or down)

## Q7 Just for fun
I had a good time teaching you all this quarter! Mishka and I will miss you.

[mishka.png](https://production-gradescope-uploads.s3-us-west-2.amazonaws.com/uploads/text_file/file/110564102/mishka.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIGIENPBVZV37ZJPA%2F20200606%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200606T191533Z&X-Amz-Expires=43200&X-Amz-SignedHeaders=host&X-Amz-Signature=661db8c689fa695ea56d0f76774744c9656db62d66e7f7394bb144f63eee89da)

### Q7.1
Do you think you'll be coding up deep learning models in the near future?

* [ ] Yes
* [x] No

### Q7.2
What was your favorite lecture?

* [ ] Introduction (history and capabilities of AI)
* [ ] Fundamentals of deep learning
* [ ] Setting up ML Projects
* [ ] Convnets and vision
* [ ] RNNs and NLP
* [ ] Transformers
* [x] Infrastructure and tooling
* [ ] Troubleshooting
* [ ] Data Management
* [ ] Testing and Deployment
