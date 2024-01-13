# Neural Machine Translation with Attention

This project implements a neural machine translation (NMT) model with attention using TensorFlow. The model translates sentences from Spanish to English. The code consists of data preprocessing, model building, training, evaluation, and inference components. Below is a detailed guide on the project structure, functionality, and usage.

## Table of Contents
- [1. Data Preprocessing](#1-data-preprocessing)
- [2. Tokenization](#2-tokenization)
- [3. Model Architecture](#3-model-architecture)
- [4. Training](#4-training)
- [5. Evaluation](#5-evaluation)
- [6. Inference](#6-inference)
- [7. Export and Load Model](#7-export-and-load-model)

## 1. Data Preprocessing
The project starts by loading bilingual sentence pairs from a file (`Data.txt`). The sentences are then split into English and Spanish components. This data is further processed through text standardization, which includes normalization, removal of special characters, and adding start and end markers.

## 2. Tokenization
The sentences are tokenized using a TextVectorization layer from TensorFlow. The tokenization is applied to both the training and testing datasets, allowing efficient padding with ragged tensors. The vocabulary size is limited to 5000 tokens.

## 3. Model Architecture
The model architecture consists of an encoder-decoder with attention mechanism. The encoder uses bidirectional GRU layers, and the decoder employs a multi-head attention layer. The model is wrapped in a `Translator` class that facilitates training and inference.

## 4. Training
The model is trained using the sparse categorical crossentropy loss function with masked padding. The training is performed for four epochs, and the model's performance is evaluated on a separate test dataset.

## 5. Evaluation
The model's performance is evaluated using the test dataset. The evaluation metrics include masked loss and masked accuracy.

## 6. Inference
The model is used for translation on individual sentences and batches. The `translate` method of the `Translator` class is utilized for this purpose.

## 7. Export and Load Model
The project includes functionality to export and load the model. Vocabularies used for tokenization are saved, and the model weights are saved to files. The model can be loaded with pre-trained weights for further translation tasks.

## Usage
To run the code, ensure you have TensorFlow and other required dependencies installed. Execute the code in a Jupyter Notebook or a Python script. The provided example demonstrates loading the model, translating individual sentences, and batch inference.

Feel free to adapt the code to your specific dataset or modify the model architecture based on your translation requirements.

Enjoy translating with your neural machine translation model!
