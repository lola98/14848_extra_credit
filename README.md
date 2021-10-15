# 14848_extra_credit

## URLs for Docker Hub images:
- xuranliu/sentiment-analysis-frontend
- xuranliu/sentiment-analysis-web-app
- xuranliu/sentiment-analysis-logic

## Steps:
1. Build docker images following the instructions in the Readme files, and push them to personal Docker Hub.
2. Create a new project on GCP.
3. Pull the docker images from Docker Hub, tag them, and push them to Container Registry.
4. Create a new Kubernete Cluster with the command 
 ```
  gcloud container clusters create \
 --machine-type n1-standard-2 \
 --num-nodes 2 \
 --zone us-central1-a \
 --cluster-version latest \
 sentimentanalysiscluster
 ```
 5. Deploy the docker images to the existing GKE cluster.
 6. Create load balancers for sa-frontend, and sa-web-app, and create a ClusterIP service for sa-logic.
 7. Update the App.js file in sa-frontend, replace "localhost" with the external IP address of the sa-web-app load balancer.
 8. In the sa-web-app pod, set environmental variable SA_LOGIC_API_URL = ip_of_sa-logic-cluster:5050.
 9. Open the ip address of the sa-frontend load balancer, and the application is successfully running.

## Video URL
https://drive.google.com/file/d/12p6xpqnUBVWR6ukBqBFJfwQo1bjeCF36/view?usp=sharing
