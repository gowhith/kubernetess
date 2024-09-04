## Prerequisite
Should have docker and java 21 setup in local

Open terminal and set path to current working directory
## Generate jar artifacts
1. Run following command to build and create artifacts required for docker
   **gradlew build**

## Generate docker images
1. Verify docker is up and running and signed in into dockerhub account
2. **docker build -t hello ./hello**
3. **docker push <dockerhub username>/hello**
4. **docker build -t world ./world**
5. **docker push <dockerhub username>/world**

## To run application in minikube
1. Install minikube based on operating system from https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download
2. Follow the steps mentioned in installation section to install minikube in local
3. Once minikube is installed, execute following commands in terminal
    1. **minikube start**
    2. **minikube kubectl -- get po -A** (this is to install kubectl)
    3. **kubectl apply -f ./hello/hello.yaml**
    4. **kubectl apply -f ./world/world.yaml**
    5. wait for all the pods to warm up and come to ready state, use following command to monitor the node status
       **kubectl get all**
    6. open new terminal and run this command to get the url for hello application -> **minikube service hello-service -n default --url**
       replace the output of above command in run.sh under HELLO_URL variable
    7. open new terminal and run this command to get the url for hello application -> **minikube service world-service -n default --url**
       replace the output of above command in run.sh under WORLD_URL variable
    8. execute **run.sh** file to make an api call to both hello and world applications and print the response in terminal

    **https://hub.docker.com/layers/gowhith12345/world/latest/images/sha256:f477c9b5a117d10cc4d0c3d79743d01470f05f0339b04d74acaaeec7acee258e?uuid=58c85301-c562-48f5-a59b-fb668bb07375%0A  - world      https://hub.docker.com/layers/gowhith12345/hello/latest/images/sha256:3d4e0f97890ba0c89fca0a312043dab56817d6d991f695e7972529dad6d37022?uuid=58c85301-c562-48f5-a59b-fb668bb07375%0A  - hello**





