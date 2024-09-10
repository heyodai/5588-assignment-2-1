# CS5588 - Assignment 2.1 Report

Full fine-tuning run is in `assignment.ipynb`. Dataset exploration is in `dataset.ipynb`.

## Model selection

We selected RoBERTa for this assignment. RoBERTa is a robustly optimized method for pretraining natural language processing (NLP) systems and builds on BERT's language masking strategy. However, it  modifies key hyperparameters, removing the next-sentence pretraining objective and training with much larger mini-batches and learning rates. We chose RoBERTa because it is a state-of-the-art model that has been shown to outperform BERT on a variety of NLP tasks while still being feasible to fine-tune on a single GPU.

## Dataset

We used the [Daily Financial News](https://www.kaggle.com/datasets/miguelaenlle/massive-stock-news-analysis-db-for-nlpbacktests) dataset from Kaggle. However, to make local training feasible, we used 1% of the dataset. The dataset contains news headlines and stock prices for 30 companies from 2008 to 2016. The goal is to predict stock price movements based on news headlines. We used the `textblob` Python library to apply sentiment analysis to the news headlines. We then used the sentiment scores as labels for the RoBERTa model.

## Results

We trained the RoBERTa model for 299 epochs and achieved a validation accuracy of ~0.85. The model was able to predict the sentiment of news headlines with high accuracy. We also visualized the training and validation loss and accuracy over time. The model was able to learn the sentiment of news headlines from the Daily Financial News dataset.

## How to Reproduce

1. Clone the repository.
2. Install the required packages using `pip install -r requirements.txt`.
3. Acquire the dataset from the [Kaggle page](https://www.kaggle.com/datasets/miguelaenlle/massive-stock-news-analysis-db-for-nlpbacktests) and place it in the `dataset` directory.
4. Run the `dataset.ipynb` notebook to preprocess the dataset.
5. Run the `assignment.ipynb` notebook to train the RoBERTa model.

## Relevance to Project

Our project involves predicting stock price movements based on news headlines. The RoBERTa model trained in this assignment can be used to predict the sentiment of news headlines. We can then use the sentiment scores as features in our stock price prediction model. The RoBERTa model can help us extract valuable information from news headlines and improve the accuracy of our stock price prediction model.
