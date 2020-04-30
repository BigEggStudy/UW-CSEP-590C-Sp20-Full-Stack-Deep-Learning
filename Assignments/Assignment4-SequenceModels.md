# Assignment 4: Sequence Models

## Q1 RNNs vs LSTMs
What is the main problem present in RNNs that LSTMs are meant to be address?

> LSTM can deal with [Vanishing Gradient Problem](https://en.wikipedia.org/wiki/Vanishing_gradient_problem). Like the ResNet for CNNs.

## Q2 Sequence Problems
Give one example of each of the following types of sequence problems:

### One-to-many:

> Music generation is a one-to-many problem, that the input will be a empty set and output the song.

### Many-to-one:

> A many-to-one problem can be high-frequency financial volatility forecasting, that the input should be a stream of quotes and trades over last few minutes and output the prediction (up or down).

### Many-to-many:

> The translation will be a many-to-many problem because the word in one language doesn't mean it still one word in another language.

## Q3 Bidirectionality
In a deep learning model developed for the machine translation task, what would be the purpose of making LSTMs bidirectional?

> For normal unidirectional LSTM, it can only learn from the information of the past because the only inputs it has seen are from the past. With bidirectional, it can run the inputs from past to future and from future to past. Then after bind the 2 hidden states, the model can preserve information from both past and future at any point in time.
>
> With bidirectional, the model can understand context better. So can be easier for the network to predict what the next word in a sentence, and this help the machine translation task a lot during the encode and decode.

## Q4 Explore in a notebook
A sentiment classification example is given in [this colab notebook](https://colab.research.google.com/drive/1S4ROAijob6bjrnAZi9eU36eZo9WEON0C?forceEdit=true&sandboxMode=true)

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

>     Model: "sequential_1"
>     _________________________________________________________________
>     Layer (type)                 Output Shape              Param #
>     =================================================================
>     embedding_1 (Embedding)      (None, None, 64)          640000
>     _________________________________________________________________
>     bidirectional (Bidirectional (None, None, 256)         197632
>     _________________________________________________________________
>     bidirectional_1 (Bidirection (None, 256)               394240
>     _________________________________________________________________
>     dense_1 (Dense)              (None, 1)                 257
>     =================================================================
>     Total params: 1,232,129
>     Trainable params: 1,232,129
>     Non-trainable params: 0
>     _________________________________________________________________

Last line of the log:

>     Epoch 10/10
>     196/196 [==============================] - 861s 4s/step - loss: 0.0883 - accuracy: 0.9724 - val_loss: 0.4978 - val_accuracy: 0.8505
