# Create kubernetes cluster and deploy spring boot app to AWS kubernetes service

### Create repository to store docker images and login into that.
aws ecr create-repository --repository-name news

##### Login to repository
aws ecr get-login --region us-east-1 --no-include-email
- output is the docker login command.

### Create image and push it to aws container registry

docker build -t [registry_id].dkr.ecr.us-east-1.amazonaws.com/news:1.0 .

docker tag {image-id} [registry_id].dkr.ecr.us-east-1.amazonaws.com/news:1.0

### push image to aws container registry.

docker push [registry_id].dkr.ecr.us-east-1.amazonaws.com/news:1.0

after pushing the image, verify the image in Amazon container services --> repositories from console.


# Create cluster and run kubernetes engine.

### Create cluster

eksctl create cluster --name news-cluster --region us-east-1

verify the cluster created from console.

### connect to cluster from local machine
aws eks --region us-east-1 update-kubeconfig --name news-cluster

### Create and run container
kubectl create -f deployment.yaml

### Copy ipaddress from services section and enter below url in browser
http://[ip_address:port]/news/feeds/test

### Run below command to scale pods
kubectl scale deployment news-service --replicas=3

### Run below command to get all the avaialble pods running
kubectl get pods

