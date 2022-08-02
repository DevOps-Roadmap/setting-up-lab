# setting-up-lab

## 1. Setting up the Lab environment on Windows 10/11

If you are using a windows laptop, its recommended that you upgrade the OS to windows 11. 

Windows 10 will also work for you, but windows 11 is much recommended.

### 1.1. Install Windows Subsystem for Linux.

Watch this video to install WSL 2 on your Windows 11 and get a Ubuntu OS running on your PC. => https://youtu.be/ysRfLJCBo_M

To know more about WSL 2, watch this video => https://youtu.be/_fntjriRe48

Once you installed WSL with Ubuntu, now you can open the Ubuntu Command Line and work on it. Any software such as kubectl, gcloud, helm etc can be installed by following the official documentation for Ubuntu OS.


### 1.2. Setup a Local Kubernetes Cluster using WSL 2 and microk8s.

Follow these instructions to run a local Kubernetes cluster on your Windows Laptop (with WSL 2) using microk8s. => https://youtu.be/DmfuJzX6vJQ

### 1.3 Install kubectl on your Windows PC.

Once you enabled WSL 2 on your Windows PC, open your Linux command line and follow the instructions of Linux Installation => https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux

### 1.4. Install gcloud Command Line on Windows with WSL 2.

Once you enabled WSL 2 on your windows PC (Ubuntu OS), open a Linux command line and follow the instructions for gcloud install on Linux  => https://cloud.google.com/sdk/docs/install#deb

