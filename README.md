# OSCONF2020ECS

Clone the repo
--------------

git clone https://github.com/debnsuma/OSCONF2020ECS.git

cd OSCONF2020ECS/flask-app-docker

Create a new image
------------------

docker build -t flask-wine-predict-app .

docker image ls

http://127.0.0.1/

Push the Image to Amazon ECR
-----------------------------

aws ecr create-repository --repository-name flask-app-docker

NOTE
=====

{account ID}.dkr.ecr.us-east-1.amazonaws.com/flask-app-docker:latest


docker tag flask-wine-predict-app:latest {account ID}.dkr.ecr.us-east-1.amazonaws.com/flask-app-docker

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin {account ID}.dkr.ecr.us-east-1.amazonaws.com/flask-app-docker

docker push {account ID}.dkr.ecr.us-east-1.amazonaws.com/flask-app-docker