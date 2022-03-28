- gcloud services enable container.googleapis.com

- gcloud container clusters create rocket --num-nodes=3 --disk-size=15 --machine-type=e2-medium
- gcloud container clusters get-credentials rocket
- gcloud container clusters delete rocket
================================================
helm repo add rocketchat-server https://rocketchat.github.io/helm-charts
kubectl port-forward rocketchat-1648421186-rocketchat-798fdbd6c5-jrg6x 7777:80
kubectl expose deployment namedeploment --type=LoadBalancer --port 80