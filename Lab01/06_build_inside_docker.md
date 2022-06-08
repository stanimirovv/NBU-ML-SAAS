### Build the service inside a Docker image
Package the service as a Docker container.
You need to:
- Install Python
- Install the dependencies
- Copy the source code
- Copy the models
- Setup the run command

You can choose whichever base image you like.

You can use this Dockerfile as a starting point:
```Dockerfile
FROM python:3.9

WORKDIR /app

COPY ./Pipfile.lock /app/Pipfile.lock

RUN pip install pipenv uvicorn
RUN pipenv sync

COPY ./main.py /app/
COPY ./svm.ml /app/

CMD ["pipenv",  "run",  "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

### Success criteria
You can run the service from a docker image and send network requests to it.