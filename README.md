# Devops-Internship-Assignment
## Github repo with ssh authentication
![alt text](https://github.com/Naveen15github/Devops-Internship-Assignment/blob/092652fa889caa9384917484720e34f51aec8f81/Screenshot%20(136).png)

## git fetch
Downlods the latest changes from the remote repository
but does not update working files
we can simply check whats new

## git pull
it downloads the changes and automatically merges them into your current branch
it directly updates your local files

## resolve a Git merge conflict (example scenario).
me and your teammate are working on the same file:index.html
my version (local branch):
< h1 >Welcome to my Website</h1>
Teammate version (remote branch):
< h1 >Hello! This is our Website</h1>
When i run:
git pull
Inside the file, Git marks the conflict like this:

<<<<<<< HEAD
< h1 >Welcome to my Website</h1>
=======
< h1 >Hello! This is our Website</h1>
>>>>>>> origin/main


The top part (HEAD) → my version

The bottom part → teammate’s version
Steps to Resolve the Merge Conflict
Step 1: Open the conflicted file

Git will show which files have conflicts:

git status

combine the correct version
<h1>Welcome to my Website</h1>
<h1>Welcome! This is our Website</h1>

Remove Git’s conflict markers:

<<<<<<<
=======
>>>>>>>
>>>>>>>

Mark the conflict as resolved
git add index.html

Complete the merge
git commit -m "Resolved merge conflict in index.html"

## Create two branches (feature-A and feature-B) and simulate a merge conflict. Resolve it and
explain the steps.
Two branches were created and both edited the same line in the same file
Merging caused a conflict because Git couldn’t decide which version to keep
Git added conflict markers <<<<<<<, =======, >>>>>>>
I manually edited the file to keep the correct content and removed markers
After resolving, I staged and committed the file to complete the merge.

## Difference between Dockerfile, Docker Image, and Docker Container
### Dockerfile
A dockerfile is a set of instructions written by us
it tells docker how to build an image
think of it like a recipe

### Docker Iamge
A docker image is the output created from the dockerfile
its like a snapshot of the application with everything installed 
it is ready only and cannot change

### Docker Container
A docker container is a running instance of the image 
it is the actual environment where your applications runs
we can start stop delete and run many containers from one image

### How to reduce Docker image size
Use smaller base images like python:3.10-slim or alpine
Avoid installing unnecessary packages
Use a .dockerignore file to ignore unwanted files
Use no cache when installing packages
Use multi-stage builds for large applications

![alt text](https://github.com/Naveen15github/Devops-Internship-Assignment/blob/092652fa889caa9384917484720e34f51aec8f81/Screenshot%20(137).png)

### Difference between Pod, Deployment and Service
Pod
A Pod is the smallest unit in Kubernetes
It contains one or more containers (like a Docker container running your app)
It can die anytime, and Kubernetes may recreate it

Deployment
A Deployment manages Pods for you
It ensures the desired number of Pods are always running
It handles replicas, rolling updates, rollbacks

Service
A Service gives network access to your Pods
It provides a stable IP and DNS name even if Pods keep restarting
Services also help with load balancing across multiple Pods

Why do we need EKS (Managed Kubernetes) instead of running Kubernetes on VMs?
Normal Kubernetes on VMs
We must manually handle:
Installation
Upgrades
Security patches
Control plane setup
Master node failure
Networking
Scaling

EKS (Managed Kubernetes)
EKS takes care of:
Control plane setup
API server, etcd, networking
Auto-scaling
Security patching
High availability
Integration with AWS services (IAM, ALB, VPC, CloudWatch)
So we only manage:
Worker nodes
Deployments/Pods/Services
































