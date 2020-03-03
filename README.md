https://hub.docker.com/_/ros
https://github.com/diegoferigo/ros-kubernetes
https://dzone.com/articles/running-local-docker-images-in-kubernetes-1
https://stackoverflow.com/questions/42564058/how-to-use-local-docker-images-with-minikube
https://kubernetes.io/docs/tasks/configure-pod-container/translate-compose-kubernetes/


minikube start --extra-config=apiserver.runtime-config=apps/v1beta1=true,extensions/v1beta1/deployments=true

eval $(minikube docker-env)

docker-compose -f build-ros-cluster.yml build

# kompose convert

kubectl apply -f master-deployment.yaml,listener-deployment.yaml,talker-deployment.yaml
