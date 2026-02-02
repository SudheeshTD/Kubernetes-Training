# Kubernetes Important Commands

=======================================================

- `minikube start --driver=docker` # Start minikube with Docker driver
- `minikube stop` # Stop minikube
- `minikube delete` # Delete minikube cluster
- `minikube delete --all --purge` # Delete all minikube clusters and purge all data
- `minikube status` # Check the status of minikube

- `kubectl version` # Check kubectl version
- `kubectl get nodes` # List all nodes in the cluster
- `kubectl get pods` # List all pods in the cluster
- `kubectl get services` # List all services in the cluster
- `kubectl describe pod <pod-name>` # Describe a specific pod

- `kuberctl run nginx-pod --image=nginx` # Create a pod with Nginx image
- `kubectl get pods` # List all pods in the cluster
- `kubectl create deployment nginx-depl --image=nginx` # Create a deployment with Nginx image.
- `kubectl get replicasets` # List all replicasets in the cluster

- Deployment manages replica sets, which in turn manage pods(which contains containers). When you create a deployment, it automatically creates a replicaset to ensure the desired number of pod replicas are running.

- `kubectl edit deployment nginx-depl` # Edit the deployment configuration

- ` kubectl exec -it mongo-depl-6c557896c-lk582 -- bin/bash` # Access the container's bash shell inside the pod
- `kubectl delete deployment mongo-depl` # Delete the deployment
- `kubectl apply -f nginx-deployment.yaml` # Apply configuration from a YAML file

-`kubectl scale rs new-replica-set --replicas=2` # Scale the replica set to 2 replicas

- `kubectl delete pod nginx-pod` # Delete a specific pod
- `kubectl describe pod nginx-pod` # Describe a specific pod

DEPLOYMENT:

- `kubectl get deployments` # List all deployments in the cluster
- `kubectl rollout status deployment/nginx-depl` # Check the rollout status of a deployment
- `kubectl rollout history deployment/nginx-depl` # View the rollout history of a deployment
- `kubectl rollout undo deployment/nginx-depl` # Rollback to the previous version of a deployment
- `kubectl set image deployment/nginx-depl nginx=nginx:1.16` # Update the image of a deployment
- `kubectl apply -f nginx-deployment.yaml` # Apply configuration from a YAML file
- `kubectl delete deployment nginx-depl` # Delete a specific deployment
- `kubectl expose deployment nginx-depl --type=NodePort --port=80` # Expose a deployment as a NodePort service
