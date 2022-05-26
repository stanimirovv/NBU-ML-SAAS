###  Training and persisting the models

Let's train two models.
The first one should be a LinearRegression. The second one should be an SVM.
You should train them on the iris dataset.
Perrsist the models in any way you like.

Relevant documentation:
https://archive.ics.uci.edu/ml/datasets/iris
https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html
https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html

If you don't want to experiment, refer to the next steps


First let's train, test and save a linear regression:

```
import pickle

from joblib import dump, load

from sklearn import datasets, linear_model
from sklearn.datasets import load_iris

X, y = load_iris(return_X_y = True)
LRG = linear_model.LogisticRegression(
   random_state = 0,solver = 'liblinear').fit(X, y)
print(LRG.score(X, y))
print(LRG.predict([[2, 0,0, 1]]))
s = pickle.dumps(LRG)

text_file = open("linear.ml", "wb")
n = text_file.write(s)
text_file.close()
```

Let's make sure the model loads correctly:
```
LRG = load('linear.ml')
print(LRG.predict([[2, 0, 0, 1]]))
```


Now let's train the SVM model:
```
SVM = svm.SVC()
X, y = datasets.load_iris(return_X_y=True)
SVM.fit(X, y)
print(SVM.predict([[20, 1, 0, 2000]]))
s = pickle.dumps(SVM)

text_file = open("svm.ml", "wb")
n = text_file.write(s)
text_file.close()

```


And finally let's make sure the SVM model loads correctly:
```
SVM = load('svm.ml')
print(SVM.predict([[2, 0, 0, 1]]))
```


### Verification
Both models should be Loadable and should