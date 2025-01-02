import itertools
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.naive_bayes import MultinomialNB
from sklearn.svm import SVC
from sklearn.neighbors import KNeighborsClassifier

# Import dataset
df = pd.read_csv('train.csv')

# Change the labels
df.loc[df['label'] == 1, 'label'] = 'FAKE'
df.loc[df['label'] == 0, 'label'] = 'REAL'

# Isolate the labels
labels = df.label

# Split the dataset
x_train, x_test, y_train, y_test = train_test_split(df['text'].values.astype('str'), labels, test_size=0.2, random_state=7)

# Initialize a TfidfVectorizer
tfidf_vectorizer = TfidfVectorizer(stop_words='english', max_df=0.7)

# Fit and transform the training set, transform the test set
tfidf_train = tfidf_vectorizer.fit_transform(x_train)
tfidf_test = tfidf_vectorizer.transform(x_test)

# Initialize and fit the Naive Bayes classifier
nb_classifier = MultinomialNB()
nb_classifier.fit(tfidf_train, y_train)

# Predict and calculate accuracy for Naive Bayes
y_pred_nb = nb_classifier.predict(tfidf_test)
score_nb = accuracy_score(y_test, y_pred_nb)
print(f'Naive Bayes Accuracy: {round(score_nb * 100, 2)}%')

# Build confusion matrix for Naive Bayes
cm_nb = confusion_matrix(y_test, y_pred_nb, labels=['FAKE', 'REAL'])
print("Naive Bayes Confusion Matrix:")
print("Our model successfully predicted", cm_nb[0][0], "positives")
print("Our model successfully predicted", cm_nb[1][1], "negatives.")
print("Our model predicted", cm_nb[0][1], "false positives")
print("Our model predicted", cm_nb[1][0], "false negatives")

# Initialize and fit the SVM classifier
svm_classifier = SVC()
svm_classifier.fit(tfidf_train, y_train)

# Predict and calculate accuracy for SVM
y_pred_svm = svm_classifier.predict(tfidf_test)
score_svm = accuracy_score(y_test, y_pred_svm)
print(f'SVM Accuracy: {round(score_svm * 100, 2)}%')

# Build confusion matrix for SVM
cm_svm = confusion_matrix(y_test, y_pred_svm, labels=['FAKE', 'REAL'])
print("SVM Confusion Matrix:")
print("Our model successfully predicted", cm_svm[0][0], "positives")
print("Our model successfully predicted", cm_svm[1][1], "negatives.")
print("Our model predicted", cm_svm[0][1], "false positives")
print("Our model predicted", cm_svm[1][0], "false negatives")

# Initialize and fit the KNN classifier
knn_classifier = KNeighborsClassifier()
knn_classifier.fit(tfidf_train, y_train)

# Predict and calculate accuracy for KNN
y_pred_knn = knn_classifier.predict(tfidf_test)
score_knn = accuracy_score(y_test, y_pred_knn)
print(f'KNN Accuracy: {round(score_knn * 100, 2)}%')

# Build confusion matrix for KNN
cm_knn = confusion_matrix(y_test, y_pred_knn, labels=['FAKE', 'REAL'])
print("KNN Confusion Matrix:")
print("Our model successfully predicted", cm_knn[0][0], "positives")
print("Our model successfully predicted", cm_knn[1][1], "negatives.")
print("Our model predicted", cm_knn[0][1], "false positives")
print("Our model predicted", cm_knn[1][0], "false negatives")

# Plotting the comparison graph
labels = ['Naive Bayes', 'SVM', 'KNN']
accuracy_scores = [score_nb, score_svm, score_knn]

plt.bar(labels, accuracy_scores)
plt.xlabel('Model')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison: Naive Bayes vs SVM vs KNN')
plt.ylim([0, 1])
plt.show()
