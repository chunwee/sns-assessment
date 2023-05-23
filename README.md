
# Building Docker Image

  

## Prerequisites

  

- Docker: Ensure that Docker is installed on your machine.

  

## Execution Steps

  

1. Create a Dockerfile in your project directory

  

2. Write the dockerfile. Add the following content:

```

FROM python:3.9

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 4000

CMD ["python", "app.py"]

```

  
  

4. Build the docker image. Open command prompt and navigate to the project directory. Run the following command to build the docker image: ```docker build -t sns-assessment .```

  
  

# Running the Docker Image

  

1. Run the Docker container using the following command: ```docker run -p 4000:4000 sns-assessment```

2. If using Postman:

- POST 127.0.0.1:4000/infer

- Under 'Body' form-data, have a key-value pair of {"image": filename}
- Click Send
- Output should say {"Classification": Model}
