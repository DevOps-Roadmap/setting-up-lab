# 1. Setting up your local Kubernetes Cluster with K3D:

**1.1 Install kubectl on Laptop**

You must install kubectl in your laptop by following the instructions at https://kubernetes.io/docs/tasks/tools/

**1.2 Install Docker Desktop on your laptop**

Download and install Docker Desktop from https://www.docker.com/products/docker-desktop/


**1.3 Start Docker Desktop.**

Start the Docker process on your laptop by opening Docker application in your laptop 


**1.4 Install k3d on your laptop**

Install K3D on your laptop by following the instructions at https://k3d.io/

**1.5 Create a K3D cluster**

Open your commandline and run below command to create a cluster. You may replace "mycluster" with your preferred name.

```
k3d cluster create mycluster
```

The command may take couple of minutes.

**1.6 Verify by creating a sample nginx pod.**

```
kubectl run nginx --image=nginx
```

You will see a message "pod/nginx created". Now you can delete the sample pod by running below command.

```
kubectl delete pod nginx
```

Well Done. Your Lap is now ready in Google Cloud




# 2. Deploying the application to GKE

**2.1 Clone the sample code from Github on your laptop**

```
git clone https://github.com/DevOps-Roadmap/frontend-project.git
```

**2.2 Change your folder to k8s/simple within the cloned folder from above step**

```
cd frontend-project/k8s/simple
```

**2.3 Create a Kubernetes Deployment for the frontend application**

```
kubectl apply -f frontend-deployment.yaml
```

**2.4 Create a kubernetes service for the frontend application**

Open the file service-frontend-lb.yaml in your favorite editor (eg: vscode) and remove the line "type: LoadBalancer". k3d cluster doesnt support LoadBalancer service like GKE. 

```
code service-frontend-lb.yaml
```

Now create the service with kubectl

```
kubectl apply -f service-frontend-lb.yaml
```

**2.5 Port forward the service to a local port (eg: 8080) on your Laptop**

```
kubectl port-forward service/coit-frontend-lb 8080:80
```

Now you can browse the URL "http://127.0.0.1:8080" on your laptop to see the deployed application.
