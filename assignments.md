## Applied Machine Language I

This assignment is included in my Applied Machine Learning I workshop.

## Assignment
Copy and paste the assignment into a new Anaconda window.

Set the k value in the KNN algorithm and identify the k values where the precision drops below:
- 90%
- 80%
- 70%

Start with a k value of 15, and then increment by 10 for each successive run. 

When you get close to a target score, start using smaller increments (stick with odd k values) until you find the proper k values.

```markdown
from sklearn.datasets import load_iris
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split

iris_dataset = load_iris()
X_train, X_test, y_train, y_test = train_test_split( iris_dataset['data'],  iris_dataset['target'],  random_state=0)
knn = KNeighborsClassifier(n_neighbors=1)

knn.fit(X_train, y_train)
print("Test set score: {:.2f}".format(knn.score(X_test, y_test)))

```



