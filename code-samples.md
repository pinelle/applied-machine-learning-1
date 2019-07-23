## Applied Machine Learning I Code Samples

These are the code samples covered in the slides for my Applied Machine Learning I workshop.

## K-Nearest Neighbors

```markdown
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier

#Characterize the iris dataset

#instantiate the iris dataset
iris_dataset = load_iris()

#Characterize the dataset
print("\n\nKeys of iris_dataset:\n", iris_dataset.keys())  
print(iris_dataset['DESCR'][:500] + "\n...") 

#characterize the data, made up of four features (columns)
print("Feature names:\n", iris_dataset['feature_names'])
print("Shape of data:", iris_dataset['data'].shape)
print("First five rows of data:\n", iris_dataset['data'][:5])

#print feature and target names
print("\nTarget names:", iris_dataset['target_names'])
print("Shape of target:", iris_dataset['target'].shape)
print("Target:\n", iris_dataset['target'],"\n")

######################################################

#Create training and testing variables from the Iris dataset

X_train, X_test, y_train, y_test = train_test_split( iris_dataset['data'],  iris_dataset['target'],  random_state=0)

print("X_train shape:", X_train.shape)
print("y_train shape:", y_train.shape,"\n")

######################################################

#Instantiate and train K-Nearest Neighbors

#Set k to 1: only use the closest neighbor
knn = KNeighborsClassifier(n_neighbors=1)
knn.fit(X_train, y_train) # train the algorithm with the training variables
KNeighborsClassifier(algorithm='auto', leaf_size=30, metric='minkowski',
           metric_params=None, n_jobs=None, n_neighbors=1, p=2,
           weights='uniform')

#Make predictions and evaluate accuracy
y_pred = knn.predict(X_test)
print("Test set predictions:\n", y_pred)
print("Test set score: {:.2f}".format(knn.score(X_test, y_test)))

```





