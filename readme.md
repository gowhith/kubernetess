

## Prerequisite
Docker: Ensure Docker is installed and running on your local machine.

Java 21: Ensure Java 21 is installed and configured on your system.

To verify your Java installation, run:
**java -version**

Docker Hub Account: Make sure you have a Docker Hub account and are logged in.

To verify Docker is running and you’re logged in:
**docker info**

Setting Up the Project
Open Terminal: Navigate to the project’s root directory.
**cd /path/to/your/project**

## Generate jar artifacts
Build the Project: Run the following command to build the project and generate the necessary JAR files:
**./gradlew build**

This command will compile your Java code, run tests, and package the application into a JAR file, which is required for creating Docker images.


## Generate docker images   
Verify Docker Setup: Ensure Docker is up and running and that you are signed in to your Docker Hub account.

Build and Push Docker Images:

Build the Hello service Docker image:
**docker build -t hello ./hello**

Push the Hello service Docker image to Docker Hub:
**docker push <dockerhub-username>/hello**
Replace <dockerhub-username> with your actual Docker Hub username.

Build the World service Docker image:
**docker build -t world ./world**

Push the World service Docker image to Docker Hub:
**docker push <dockerhub-username>/world**
Replace <dockerhub-username> with your actual Docker Hub username.


## To run application in minikubenstall Minikube:

Install Minikube based on your operating system.
**brew install minikube**
Start Minikube:

After installation, start Minikube by running:
**minikube start**

Install kubectl:

If kubectl is not installed, install it by running:
**minikube kubectl -- get po -A**
Deploy the Services:

Deploy the Hello service:
**kubectl apply -f ./hello/hello.yaml**

Deploy the World service:
**kubectl apply -f ./world/world.yaml**

Monitor Pods and Services:
Wait for the pods to warm up and come to a ready state. You can monitor the status by running:
**kubectl get all**

Obtain Service URLs:
Get the URL for the Hello service:
**minikube service hello-service -n default --url**

Copy the output URL and replace it in the run.sh script under the HELLO_URL variable.
Get the URL for the World service:
**minikube service world-service -n default --url**
Copy the output URL and replace it in the run.sh script under the WORLD_URL variable.

Execute the run.sh Script:

Once the URLs have been set, run the run.sh script to make API calls to both the Hello and World services and print the combined "Hello World" message in the terminal:

Convert run.sh to an Executable Script
Create the run.sh File: Copy the above script into a file named run.sh.
**chmod +x run.sh**
Run the Script: You can now execute the script directly by typing:
**./run.sh**





##Docker images to Docker Hub:-

hello : 
  [https://hub.docker.com/layers/gowhith12345/hello/latest/images/sha256:3d4e0f97890ba0c89fca0a312043dab56817d6d991f695e7972529dad6d37022?uuid=58c85301-c562-48f5-a59b-fb668bb07375%0A]
   
   **gowhith12345/hello**

world : 
  [https://hub.docker.com/layers/gowhith12345/world/latest/images/sha256:f477c9b5a117d10cc4d0c3d79743d01470f05f0339b04d74acaaeec7acee258e?uuid=58c85301-c562-48f5-a59b-fb668bb07375%0A]     
   **gowhith12345/world**





