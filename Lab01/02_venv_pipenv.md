### Virtual Environment

```
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install pipenv
```

Let's populate the Pipfile and Pipfile.lock with some packages:
```
pipenv install fastapi
pipenv install "uvicorn[standard]" sklearn
```

### Verification

Pipfile and Pipfile.lock files should be created.
They should contain fastapi and uvicorn.