# Cyber-Intrusion-Detection

This model uses quantum machine learning to predict intrusion over a network using PCAP data. The model classified betweent 31 models, however during stratified downsampling certain classes get removed at the no of samples is less, those classes are combined into one class named "other" totaling 27 classes.

Dataset: https://www.kaggle.com/datasets/daniaherzalla/tii-ssrc-23

QML_PRE: use this dataset to downsample the dataset from 7252154 samples to 100000 (or any number set by the user). This code splits into 2 datasets train and test (80:20) and perform angle embedding on them to prepare for qml

QML_COMMON: this code takes the split data and performs Princiapl component analysis on the dataset to reduce to n number of qubits(=no of features) to make the qml training feasible as well as another layer of stratified downsampling to desired number of samples for efficient training. (not every model required all samples and features for high accuracy). Use this code as a preffix to all model training (i.e. feed the output x_train_pca and x_test_pca into the training and testing phases).
