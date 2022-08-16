# How to run

cd react-docker
npm i
npm run build
docker build -t your_docker_username/react-docker .
docker run -d -p 3000:80 your_docker_username/react-docker
cd ../K8s
minikube start
kubectl create namespace react-docker
kubectl config set-context --current --namespace=react-docker
kubectl apply -f deployment.yaml
kubectl apply -f load-balancer.yaml
kubectl get deployment -w
kubectl get services -w
