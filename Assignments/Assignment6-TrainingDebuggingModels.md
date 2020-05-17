# Assignment 6: Training & Debugging Models

## Q1 Troubleshooting Training
In the course of working on a single project, you encounter several different scenarios.

### Q1.1
Scenario 1: training loss goes down to 0, validation loss goes down to 5.

Select the next best action:

* [ ] Double-check code and dataset
* [x] Increase regularization of the network (e.g. add dropout)
* [ ] Increase capacity of the network (e.g. add more layers)
* [ ] Increase learning rate

### Q1.2
Scenario 2: training loss goes down to 5, validation loss goes down to 5.

Select the next best action:

* [ ] Double-check code and dataset
* [ ] Increase regularization of the network (e.g. add dropout)
* [x] Increase capacity of the network (e.g. add more layers)
* [ ] Increase learning rate

### Q1.3
Scenario 3: training loss goes down to 5, validation loss goes down to 0.

Select the next best action:

* [x] Double-check code and dataset
* [ ] Increase regularization of the network (e.g. add dropout)
* [ ] Increase capacity of the network (e.g. add more layers)
* [ ] Increase learning rate

## Q2 Cross-Entropy Loss

Here is the definition of the cross-entropy loss function, with {y}_i being the one-hot vector indicating the class of item *i*, and \hat{y}_i being the vector of activation scores output by the neural network for item *i*.

J = - \frac{1}{N}(\sum_{i=1}^{N} \mathbf{y_i} \cdot log(\mathbf{\hat{y}_i}))J

Which of the following changes in the activation scores would decrease the loss? Select all that apply.

* [x] Activation scores for the correct class increase
* [ ] Activation scores for the correct class decrease
* [ ] Activation scores for the incorrect classes increase
* [x] Activation scores for the incorrect classes decrease
