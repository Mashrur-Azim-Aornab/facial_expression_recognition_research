In this project, a Convolution-based(CNN) deep learning model is trained to identify facial expressions from images. The expressions the model has to recognize are "Angry","Disgust","Fear","Happy","Neutral","Sad", and "Surprise".
A total of 3 datasets from Kaggle was used in this project. Dataset sources are as follow:
(1) https://www.kaggle.com/datasets/samithsachidanandan/human-face-emotions
(2) https://www.kaggle.com/datasets/msambare/fer2013
(3) https://www.kaggle.com/datasets/furcifer/fane-facial-expressions-and-emotion-dataset
The train dataset consisted of all the images from dataset 1 and dataset 3. However, the dataset 2 contributed to both train set and the test set. 
All the images were reshaped to have size (1,224,224) and have a mean of 0.5 and standard deviation of 0.5 across their only one channel.
The test dataset was later divided into test set and validation set. 80% of the test dataset contributed to test and the remaining images formed the validation set.
To address the inconsistency among the class labels' frequency in the train set, WeightedRandomSampler was used in the train-DataLoader. 
The batch size was 32 for all of test set, train set, and validation set. 

The CNN model consists of 4 convolution layers and 2 fully connected layers for classification. The last fully connected layer in the CNN model has 7 neurons since the model has to identify among 7 facial emotions.
In the other words, the featurizer in the CNN model has 4 convolution layers and the classifier has 2 fully connected layers.

The model was trained for a total of 33 epochs and while training, the best model was identified each time a better validation accuracy was found in a particular epoch.
The final best model from epoch 33 had a validation accuracy of 85.2265%. The best model's performance accuracy on the test set was 85.2690%.
