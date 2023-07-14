# Neural Network Model for Popularity Prediction
This repository contains the code for training and evaluating a neural network model for predicting the popularity of songs. The model is built using TensorFlow and Keras and utilizes the RMSprop optimizer with a learning rate of 0.001.

# Data
The dataset used for training and testing the model is loaded from the "modified_data.csv" file. The dataset includes various features of songs such as duration, explicitness, danceability, energy, key, loudness, mode, speechiness, acousticness, instrumentalness, liveness, valence, tempo, genre ID, time signature, and artist ID.

# Model Architecture
The neural network model consists of several dense layers with ReLU activation. The number of neurons in each dense layer is determined by the layerThiccness parameter, which is calculated as twice the number of columns in the dataset. The last layer has a single neuron, which predicts the popularity of a song.

# Data Preprocessing
Before training the model, the training and test data are split using a test size of 20%. The data is then converted to TensorFlow tensors and normalized using mean normalization. The mean and standard deviation used for normalization are calculated from the training data.

# Model Training
The model is trained for 100 epochs with a batch size determined by the data size. During training, the mean absolute error (MAE) is used as the loss function, and the MAE and mean squared error (MSE) are recorded as metrics. The training progress is visualized by plotting the MAE for both the training and validation sets.

# Model Evaluation
After training, the model is evaluated on the test data. The mean absolute error (MAE) is calculated and printed as a measure of the model's performance on unseen data. Additionally, the mean squared error (MSE) is computed to assess the overall prediction accuracy.

# Error Analysis
The histogram of error distribution shows that errors in the range of 0 to approximately 15 points are almost equally frequent. This suggests that the model achieves a good fit to the given data. However, it also indicates that the data alone is not sufficient to make significantly better predictions, as the model cannot capture the inherent variability and other factors affecting song popularity.

It is noteworthy that the best-performing model, despite achieving the lowest mean error, exhibits the least consistency in its performance and shows a deterioration of test results compared to the training results. This may indicate the occurrence of overfitting, which is not observed in the other model variations.

In the case of other models where the difference between test error and training error is smaller, it can be inferred that the models are better regularized and more capable of generalization. This suggests that these models are less dependent on the training data and can handle new data more effectively, which is desirable.

# Conclusion
Based on the task of predicting song popularity using the provided Spotify dataset, it can be concluded that the current state of the neural network model is not sufficient for effective prediction.

One of the major challenges is the presence of numerous other factors influencing song popularity, such as production quality, record label, or promotional campaigns. These factors, while separate from the song itself, have a significant impact on its popularity. Expanding the dataset to include a wider range of songs from different artists could help address some of these factors and provide a more comprehensive basis for predicting song popularity.

Considering the results of the model and the significant improvement achieved through expansion and refinement, it can be concluded that the developed neural network utilizes the available data to its potential. It may be more appropriate to view the results as an indication of a song's potential for popularity, as there are many factors not captured in the dataset that can have a substantial impact on a song's popularity.
