# Assignment 2: ML Projects

## Q1 Bias vs Variance

### Q1.1
When a trained model is said to be “high bias”, is it underfit or overfit on the training set?

* [x] underfit
* [] overfit

### Q1.2
Explain the concept of bias-variance tradeoff. Does it apply to deep neural networks (explain why or why not)?

> If the model is too simple and has very few parameters then it will be high bias and low variance. On the contract, if the model has so many parameters, it will be high variance and low bias. So we need to make sure our model should not too simple or too complicate.
>
> I think the bias-variance tradeoff should also applied to deep neural networks. Although in modern practice, very rich models such as neural networks are trained to exactly fit (i.e., interpolate) the data. And this often obtain high accuracy on test data even they should be considered as overfit.
>
> We can have a simple example to illustrate this: if our model have almost unlimited nodes it can accurately remember all the training data, and that will give us overfitting which will still have a high variance.
>
> And the reason why people find there have a gap between mathematical foundations of machine learning and the Deep Learning practice, I think, is because: it might not as easy as normal regression problems that can use a simple formula to compute them in Deep Learning. 
>
> * In this article: [A Modern Take on the Bias-Variance Tradeoff in Neural Networks](https://arxiv.org/abs/1810.08591), it introduce a new decomposition of the variance to disentangle the effects of optimization and data sampling.
>
> * And in this article: [Reconciling modern machine-learning practice and the classical bias–variance trade-off](https://www.pnas.org/content/116/32/15849), they use a “double-descent” curve to show how increasing model capacity beyond the point of interpolation results in improved performance.

## Q2 Software 2.0
In your own words, explain how "Software 2.0" (Andrej Karpathy's term we mentioned in lecture), or training ML models, is different from Software 1.0, or traditional software engineering.

> 

## Q3 Identifying Offensive Photos Case Study
You are working at a company that runs a popular discussion forum, where users can upload an avatar photo. It is important to the company that the avatar photos are not offensive to other users, so a team of avatar reviewers looks through all uploaded photos and removes offensive ones.

It is very important to the company that every single offensive photo is removed, but the cost of running the avatar team is getting very expensive. You are tasked with developing a computer vision system to help the team identify offensive photos. The business goal is to keep the size of the team constant while scaling the forum from its current 1M users to 100M users in the next few years.

### Q3.1 Metric
What metric or metrics will you work to optimize as you work on the project?

Here is a helpful table of many other different metrics possible to derive from the confusion matrix. For this project, predicting that a photo is offensive is called a “positive” prediction. If the photo is actually offensive, that is called a “positive” true condition.

![Confusion Matrix](https://s3-us-west-2.amazonaws.com/gradescope-static-assets/fsdl/conf_table.png)

>

### Q3.2 Dataset Split
To date, the avatar reviewers have looked at 1,000,000 uploaded photos, and found 10,000 (1%) to be offensive. Assume that the team is 100% accurate.

What are reasonable choices for splitting this data into training/validation/test sets?

* [] 20% to training, 40% to validation, 40% to test
* [] 20% to training, 20% to validation, 60% to test
* [] 50% to training, 25% to validation, 25% to test
* [] 50% to training, 49% to validation, 1% to test
* [x] 80% to training, 10% to validation, 10% to test
* [] 98% to training, 1% to validation, 1% to test

### Q3.3 Dataset Split part 2
What are reasonable choices for assigning examples that are labeled as offensive (“positive”) to training/validation/testing?

* [x] According to the overall distribution
* [] Evenly across training/validation/test, no matter what the overall distribution is
* [] Evenly across the validation and test datasets
* [] All to the test dataset

### Q3.4
You came across a public dataset that another company put together for the same task. The dataset consists of 500,000 photos, with 5,000 (1%) labeled as offensive.

The data distribution in this dataset is similar but not the same: their forum is for anime fans, whereas yours is for software developers.

Regardless, you want to add this data to your company's proprietary dataset.

Select the best option for doing this:

* [x] Distribute the new photos into training/validation/testing sets following the same distribution as you selected in the previous question
* [] Add the new photos to the training set only
* [] Add the new photos to the validation set only
* [] Add the new photos to the test set only
