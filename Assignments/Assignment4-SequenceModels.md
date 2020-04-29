# Assignment 4: Sequence Models

## Q1 RNNs vs LSTMs
What is the main problem present in RNNs that LSTMs are meant to be address?

## Q2 Sequence Problems
Give one example of each of the following types of sequence problems:

### One-to-many:

### Many-to-one:

### Many-to-many:

## Q3 Bidirectionality
In a deep learning model developed for the machine translation task, what would be the purpose of making LSTMs bidirectional?

## Q4 Explore in a notebook
A sentiment classification example is given in this colab notebook

Make sure you understand what's going on, and try at least one of the things suggested in the last cell.

When you do, paste in your model summary and your final training log line.

Like this:

>     Model: "sequential"
>     _________________________________________________________________
>     Layer (type)                 Output Shape              Param #
>     =================================================================
>     embedding (Embedding)        (None, None, 64)          640000
>     _________________________________________________________________
>     lstm (LSTM)                  (None, 128)               98816
>     _________________________________________________________________
>     dense (Dense)                (None, 1)                 129
>     =================================================================
>     Total params: 738,945
>     Trainable params: 738,945
>     Non-trainable params: 0
>     _________________________________________________________________

>     Epoch 6/6
>     196/196 [==============================] - 11s 57ms/step - loss: 0.1143 - accuracy: 0.9599 - val_loss: 0.4202 - val_accuracy: 0.8530

Model summary:

Last line of the log:
