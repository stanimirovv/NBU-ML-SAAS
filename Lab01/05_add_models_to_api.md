### Add the models to the API

Make an API call that receives as arguments the 4 parameters required by the dataset and returns the prediction.

You have freedom how to implement the API.

Bellow is an example implementation with some TODO's if you don't want to start from scratch:
Note: This API really isn't complete - parameter names are bad, there is no logging, there is no error handling.
Feel free to expand it. 

```python
import pickle

from fastapi import FastAPI
from joblib import dump, load
from sklearn import datasets, linear_model, svm
from sklearn.datasets import load_iris

app = FastAPI()

SVM = load('svm.ml')
print(SVM.predict([[2, 0, 0, 1]]))


@app.get("/")
async def root():
    return {"message": "Hello World"}


@app.get("/iris")
async def root(a, b, c, d):
    # TODO put goot names
    # TODO validate input
    prediction = int(SVM.predict([[a, b, c, d]])[0])
    response = {"class": prediction}
    return response
```



### Success criteria
The API can be queried by curl and returns correct response.