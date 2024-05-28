# Flask Hello World API

This project is a simple Python API server built using Flask. The API returns a JSON response with a return code and a "hello world" message. The application is containerized using Docker.

## Table of Contents

- [Project Description](#project-description)
- [Setup Instructions](#setup-instructions)
- [Building and Running the Docker Container](#building-and-running-the-docker-container)
- [Using the API](#using-the-api)

## Project Description

This project demonstrates a basic API server using Flask. The server has a single endpoint that returns a JSON response. The project also includes a Dockerfile to containerize the application for easy deployment.

## Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/wahyumuqsita/simple-api-server.git
   cd flask-hello-world-api
   ```

2. **Edit `app.py`**:
   Ensure you have the following code in `app.py`:
   ```python
   from flask import Flask, jsonify

   app = Flask(__name__)

   @app.route('/hello', methods=['GET'])
   def hello_world():
       response = {
           "return_code": 200,
           "message": "hello world"
       }
       return jsonify(response)

   if __name__ == '__main__':
       app.run(host='0.0.0.0', port=5000)
   ```

## Building and Running the Docker Container

1. **Build the Docker image**:
   ```bash
   docker build -t flask-hello-world .
   ```

2. **Run the Docker container**:
   ```bash
   docker run -p 5000:5000 flask-hello-world
   ```

## Using the API

After running the Docker container, the API will be accessible at `http://localhost:5000/hello`. You can test the endpoint using a web browser, `curl`, or Postman.

Example response:
```json
{
  "return_code": 200,
  "message": "hello world"
}
```

### Testing with `curl`:
```bash
curl http://localhost:5000/hello
```
