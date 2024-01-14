

## Python-flask-Deployment-Aws
## python-flask: This is a python-flask project that shows the deployment of python flask on Aws, it further demonstrates the use of docker to build docker image, shows docker containnerisation.The Dockerfile was created to be able to build the flask_app docker image. Once built i ran the command below to show the numbers of docker images 
available locally

##set up

Create the project folder
Create the application launch file app.py
Create the templates folder to contain all the html files
Create the requirement.txt continuing all the libraries for the project
Create .dockerignore
Create .gitignore
Create the Dockerfile
Create the docker-compose.yml file


## first check if there are any local images  on your system, run the command below

$docker images 

After creating the docker images using the Dockerfile we now need to run the container using the

$ docker run -d <dockerimages>

$docker run -p 5002:5002 <dockerimages>

$docker container ls

CONTAINER ID   IMAGE       COMMAND            CREATED         STATUS         PORTS                    NAMES
b7e8a93a83c9   flask_app   "python3 app.py"   2 minutes ago   Up 2 minutes   0.0.0.0:5002->5002/tcp   stupefied_mirzakhani

To access the container from the inside

$ docker exec -it <imagename>  /bin/bash

docker exec -it <containerID> /bin/bash

## we are now inside the container

root@61aff23db01e:/app# ls

Dockerfile  app.py  requirement.txt

root@61aff23db01e:/app# exit


Now to use docker-compose to lunch the application

Make sure you have docker-compose.yml file written

$ docker-compose up -d

## Now check if the container is build already

$docker container ls


## to run the container use the command below

$docker-compose logs
 $docker-compose logs -f

=================================

## To remove docker images

sudo docker rmi  <imagename>

## to force delete any image

$docker rmi -f  <imagename>

$sudo rmi <imagename>
## how to remove  container


## To remove the container, run the command below
$ docker-compose down

## Or try  removing the conatiners individually use the  below command

$sudo docker rm -f <container ID>

# To be sure it has removed the containers run the command

 $ docker container ls