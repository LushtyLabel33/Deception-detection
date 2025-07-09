------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
MODEL IMPLEMENTATION AND DESCRIPTION

This folder contains three baseline implementations for deception detection on the Diplomacy dataset:

1. Human Baseline:
   Compares the sender’s intended annotations with the receiver’s perceived annotations. Evaluation is based on Macro F1, Lie F1 (F1 score for the deceptive class), and overall Accuracy.

2. Classical Machine Learning Models:
   Implements a suite of classical ML models using a Bag-of-Words (BoW) representation of the messages. The models include:
   - Logistic Regression
   - Support Vector Machine (SVM)
   - k-Nearest Neighbors (KNN)
   - Decision Trees
   - Random Forest  
   Each model is configured with balanced class weights to handle severe class imbalance.

3. Deep Learning Models: 
   Implements three deep learning architectures using bidirectional recurrent neural networks. It tokenizes the texts, pads them, and then trains the models on the train, validation, and test splits. Following Model has been implemented:
   - Bi-RNN
   - Bi-LSTM
   - Bi-GRU  
   Texts are tokenized using the Keras Tokenizer and padded to a fixed length before being fed into the models. Evaluation metrics include Test Accuracy, Macro F1, and Lie F1.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
DATASET DESCRIPTION

The Diplomacy dataset is provided in JSONLines format where each line represents a full game dialog. Each dialog includes the following key fields:

- messages: A list of message strings.

- sender_labels: The sender’s annotation indicating if the message is intended as truthful (true) or deceptive (false).

- receiver_labels: The receiver’s annotation indicating if the message is perceived as truthful (true), deceptive (false), or "NOANNOTATION" if missing.

- Additional Metadata: Includes game scores, score differentials, message indices, season, year, and game_id.

For all baselines, the focus is on comparing sender and receiver annotations after appropriate filtering and preprocessing.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 

All the models are stpred in .ipynb file. To run any of the files, configure and set kernel to Python 3.12.4 version and just run the cells. Ensure that the dataset and path are correctly configured 