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
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
flask-sample        latest              c1b7a8a29e9b        10 seconds ago      53.3MB
python              3.8.5-alpine        0f03316d4a27        45 hours ago        42.7MB
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
 * Debugger PIN: 171-688-111
172.17.0.1 - - [10/Sep/2020 17:41:31] "GET / HTTP/1.1" 200 -
```
## Cleanup

Stop and remove the container
```
docker rm -f flask-web
```

Optionally, remove the create image
```
docker rmi flask-sample
```





