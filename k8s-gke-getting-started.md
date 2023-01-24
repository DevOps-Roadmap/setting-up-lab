# 1. Setting up your Kubernetes Cluster in Google Cloud:

## 1.1 Install kubectl on Laptop

You must install kubectl in your laptop by following the instructions at https://kubernetes.io/docs/tasks/tools/

## 1.2 Install gcloud commandline

You must install gcloud in your laptop by following the instructions at https://cloud.google.com/sdk/docs/install

## 1.3 Initiate the gcloud connection with Google.

You must execute the below command and login to initialize the gcloud cli tool. 

```
gcloud init
```

## 1.4 Create a Kubernetes cluster at GKE using gcloud

```
gcloud container clusters create cluster-1
```

You may replace cluster-1 with your own name. 

## 1.5 Verify by creating a sample nginx pod.

```
kubectl run nginx --image=nginx
```

You will see a message "pod/nginx created". Now you can delete the sample pod by running below command.

```
kubectl delete pod nginx
```

Well Done. Your Lap is now ready in Google Cloud




# 2. Deploying the application to GKE

## 2.1 Clone the sample code from Github on your laptop

```
git clone https://github.com/DevOps-Roadmap/frontend-project.git
```

## 2.2 Change your folder to k8s/simple within the cloned folder from above step

```
cd frontend-project/k8s/simple
```

## 2.3 Create a Kubernetes Deployment for the frontend application 

```
kubectl apply -f frontend-deployment.yaml
```

## 2.4 Create a kubernetes service with a public IP for the frontend application

```
kubectl apply -f service-frontend-lb.yaml
```

## 2.5 Wait for a minute until the public IP is ready and run below command to get the public IP

```
kubectl get services
```

Get the public IP in the output and try to browse it from a browser. You should see a simple webpage.
