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



## Running the Project with Kubernetes



Kubernetes helps manage containerized applications. For this project, Minikube is used to run a local Kubernetes cluster.



## Main Kubernetes Components



Pod: Runs the application container.



Deployment: Manages Pods and makes sure the required number are running.



Service: Provides a stable way to access the application and route traffic to its Pods.



## Deployment Steps



Start Minikube:



minikube start --driver=docker



Load the Docker image:



minikube image load cloud-service-demo:1.0



Apply the Kubernetes Deployment and Service:



kubectl apply -f kubernetes/deployment.yaml

kubectl apply -f kubernetes/service.yaml



Access the application:



kubectl port-forward service/cloud-service-demo 8081:80



Open http://localhost:8081 in your browser.



The Kubernetes configuration files are stored in the kubernetes folder.

