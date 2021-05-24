# flask-sample
Sample Dockerized Flask Application

## Dependencies

Docker

## Running the application

Step 1: Build docker image using remote context 
```bash
docker build -t flask-sample https://github.com/maroskukan/flask-sample.git
```

Step 2: Verify the image
```bash
docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
flask-sample        latest              c1b7a8a29e9b        10 seconds ago      53.3MB
python              3.8.5-alpine        0f03316d4a27        45 hours ago        42.7MB
```

Step 3: Run the container
```bash
docker run -d -p 5000:5000 --name flask-web flask-sample
```

## Verifying the application

Step 1: Verify the application using curl
```html
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
```bash
docker container logs flask-web
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 171-688-111
172.17.0.1 - - [10/Sep/2020 17:41:31] "GET / HTTP/1.1" 200 -
```
## Cleanup

Step 1: Stop and remove the container
```bash
docker rm -f flask-web
```

Step 2: Optionally, remove the create image
```bash
docker rmi flask-sample
```





