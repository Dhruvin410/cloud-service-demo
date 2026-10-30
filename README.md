# cloud-service-demo

## Purpose

the basic idea about github and h0w to host a project in cloud

## Files included

* README.md: basic info
* index.html: basic code

## Version control

tracking every change made to the application code and cloud infrastructure templates



**Running the project with Docker**



Docker allows an application to run inside a container with the files and dependencies it needs. A Docker image is the packaged template used to create a container, while a container is the running instance of that image.



**Build the Docker image**



docker build -t cloud-service-demo:1.0 .



**Run the container**



docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0



Once the container is running, open http://localhost:8080 in a web browser to view the application.



**Check running containers**



docker ps

