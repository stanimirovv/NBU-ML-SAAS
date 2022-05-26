## Create API with Flask or FastAPI

Create a hello world application with fastapi.
Relevant documentation: https://fastapi.tiangolo.com/

Create a file called main.py and write in it:
```
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
async def root():
    return {"message": "Hello World"}
```
    