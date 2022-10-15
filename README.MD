# Kubernetes Deployment of Dockerized React App

This repo has only single file consisting all the configurations required to deploy a docker container having a Single Page Application using React.js

You can follow the steps mentioned in this repository in order to create a docker image of react app and pushing it on docker hub followed by pulling the image and running it on your device: https://github.com/tanishq252/dockerreact/tree/master

Once done with above mentioned steps we can proceed to create a Kubernetes Cluster using minikube.

Your system should have minikube installed to execute the following commands!

Follow further steps to create pods of the docker image and orchestrate them using kubernetes:

- First of all we have to make sure our container is running properly

            docker ps -a