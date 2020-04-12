# Lab 1: Single-character prediction

## Before you begin, make sure to set up!

Please complete [Lab Setup](/setup.md) before proceeding!

## Goal of the lab

Train a model to solve a simplified version of the line text recognition problem.

## Outline

- Intro to EMNIST, a character prediction dataset.
- Explore the `networks` and `training` code.
- Train simple MLP/CNN baselines to solve EMNIST.
- Test your model.

## Follow along

```
git pull
cd lab1/
```

## Intro to EMNIST

- EMNIST = Extended Mini-NIST :)
- All English letters and digits presented in the MNIST format.
- Look at: `notebooks/01-look-at-emnist.ipynb`

## Networks and training code

```
- text_recognizer/networks/mlp.py
- text_recognizer/networks/lenet.py
- text_recognizer/models/base.py
- text_recognizer/models/character_model.py
- training/util.py
```

## Train MLP and CNN

You can run the shortcut command `tasks/train_character_predictor.sh`, which runs the following:

```sh
training/run_experiment.py --save \
  '{"dataset": "EmnistDataset", "model": "CharacterModel", "network": "mlp",  "train_args": {"batch_size": 256}}'
```

It will take a couple of minutes to train your model.

Just for fun, you could also try a larger MLP, with a smaller batch size:

```sh
training/run_experiment.py \
  '{"dataset": "EmnistDataset", "model": "CharacterModel", "network": "mlp", "network_args": {"num_layers": 8}, "train_args": {"batch_size": 128}}'
```

Let's also train a CNN on the same task.

```sh
training/run_experiment.py '{"dataset": "EmnistDataset", "model": "CharacterModel", "network": "lenet", "train_args": {"epochs": 1}}'
```

Training the single epoch will take about 2 minutes (that's why we only do one epoch in this lab :)).
Leave it running while we go on to the next part.

It is very useful to be able to subsample the dataset for quick experiments.
This is possibe by passing `subsample_fraction=0.1` (or some other fraction) at dataset initialization, or in `dataset_args` in the `run_experiment.py` dictionary, for example:

```sh
training/run_experiment.py '{"dataset": "EmnistDataset", "dataset_args": {"subsample_fraction": 0.1}, "model": "CharacterModel", "network": "lenet"}'
```

## Testing

First, let's take a look at how the test works at

```
text_recognizer/tests/test_character_predictor.py
```

Now let's see if it works by running:

```sh
pytest -s text_recognizer/tests/test_character_predictor.py
```

Or, use the shorthand `tasks/test_functionality.sh`

Testing should finish quickly.
