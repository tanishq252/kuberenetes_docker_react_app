# Kubernetes Deployment of Dockerized React App

This repo has only single file consisting all the configurations required to deploy a docker container having a Single Page Application using React.js

You can follow the steps mentioned in this repository in order to create a docker image of react app and pushing it on docker hub followed by pulling the image and running it on your device: https://github.com/tanishq252/dockerreact/tree/master

Once done with above mentioned steps we can proceed to create a Kubernetes Cluster using minikube.

Your system should have minikube installed to execute the following commands!

Follow further steps to create pods of the docker image and orchestrate them using kubernetes:

- First of all we have to make sure our container is running properly

            docker ps -a
            
![image](https://user-images.githubusercontent.com/78098329/195972083-254eca2d-f731-46b1-af86-7aec8527b633.png)

- Copy the container id and run following command to restart the container

            docker run <Container ID>
            
 ![image](https://user-images.githubusercontent.com/78098329/195972206-b4f24e3a-a84b-49c6-aca5-135aaf3a1cc1.png)

- The above commands ensure that container is running so we can proceed further by starting minikube, make sure you run the following command in the directory where the *deployment.yaml* file is present.

            minikube start
            
- Once minikube is successfully started, and *deployment.yaml* file is configured as per our requirements, run the following command.

            kubectl apply -f deployment.yaml
  
If you get the same result as the below image the service for the container has been created and pods for the container will start running!
![image](https://user-images.githubusercontent.com/78098329/195972610-c863b8f4-74c9-4ffe-a332-d00715d0ec7d.png)

- Run this command to ensure that pods for our container are running successfully

            kubectl get pods
            
![image](https://user-images.githubusercontent.com/78098329/195972734-d4f88bd8-4200-427e-9f75-4d9342529cc5.png)

- To get the current running services

            kubectl get svc
            
![image](https://user-images.githubusercontent.com/78098329/195972828-8cacd984-768b-4793-81fe-8ef02c645582.png)

- You can try various commands to check the status of your pods as mentioned below

            kubectl describe pod <service name>
            
![image](https://user-images.githubusercontent.com/78098329/195972870-aab4b235-a68b-4560-ad37-101e823e3970.png)

- Once we are done with checking all the statistics of the pod we can proceed to check whether the external service of our pod is running successfully or not.
- Run following command to generate the url of the service we want

            minikube service <service name> --url
            
![image](https://user-images.githubusercontent.com/78098329/195973324-6f449bf8-61c9-4b1a-9863-aa83b4325931.png)

- You can click on generated link and check whether your application is working properly or not

- If all the steps have been successfully executed and user interface of your react app is visible then CONGRATULATE YOURSELF ;)

- As the architecture of Kubernetes works in a beautiful way, after running pods successfully you can open the kubernetes dashboard and explore the architecture properly since you have a real time cluster running on your system.

- Run the following command

            minikube dashboard
            
- Dashboard will look like this!
            
![image](https://user-images.githubusercontent.com/78098329/195973594-f7cef4da-fd7f-4626-ad60-daadb5077282.png)

Further you can refer to official documentation of Kubernetes to understand how we can have environment variables whenever working with applications using database.

To see how yaml files of mongo db based application has to be configures, refer code from this repository: https://github.com/tanishq252/kubernetes-mongo-app-deployment

Happy Coding :)

            
