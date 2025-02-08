# Emotion-Recognition-Model-With-LSTM
This code uses a deep learning-based model to determine the emotional tone of a given sentence. The LSTM-trained model vectorizes the text and classifies it into one of six different emotion categories. It makes emotion predictions by optimizing the model with training and test data.

✨Project Objective
The goal of this project is to determine the emotional tone of given sentences. The model is trained to classify six different emotion categories:
Joy, Anger, Love, Sadness ,Fear and Surprise.

🧾Dataset
The project utilizes a dataset containing sentences and their corresponding emotion labels. The dataset is loaded from train.txt, test.txt, and val.txt files.

🖥️ Model Details
->Word Embedding: Text data is vectorized using a word embedding approach.
->LSTM: Long Short-Term Memory (LSTM) networks are used to capture emotional context.
->Fully Connected Layer: LSTM outputs are passed through a fully connected layer for classification.
->Optimization: The Adam optimization algorithm is used.
->Loss Function: Cross-entropy loss (CrossEntropyLoss) is applied.
![applsci-10-05841-g004-550](https://github.com/user-attachments/assets/17422c63-4d33-461d-b369-7ca626676ac0)
