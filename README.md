# flask-sample
Sample Dockerized Flask Application

## Dependencies

Docker

## Running the application

Step1: Clone this repository.
```
git clone https://github.com/maroskukan/flask-sample.git
```

Step 2: Navigate to src/ folder and build docker image
```
cd flask-sample/src
docker image build -t flask-sample .
```

Step 3: Verify the image
```
docker image ls
```

Step 4: Run the container
```
docker run -d -p 5000:5000 --name flask-web flask-sample
```

## Verify the application
Step 1: Verify the application using curl
```
curl http://localhost:5000
<!DOCTYPE thml>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>dockerize flask app</title>
</head>
<body>
    <h1> Hello World! </h1>
</body>
```

Step 2: Verify application logs
```
docker container logs flask-web
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 145-213-795
172.18.0.1 - - [10/Sep/2020 17:17:34] "GET / HTTP/1.1" 200 -
172.18.0.1 - - [10/Sep/2020 17:17:34] "GET /favicon.ico HTTP/1.1" 404 -
172.17.0.1 - - [10/Sep/2020 17:31:43] "GET / HTTP/1.1" 200 -
```
## Cleanip
Simple stop and remove the created container
```
docker stop flask-web
```





