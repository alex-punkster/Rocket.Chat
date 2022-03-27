gcloud services enable container.googleapis.com
gcloud container clusters create rocket --num-nodes=2 --disk-size=15 --machine-type=e2-medium
gcloud container clusters get-credentials rocket
gcloud container clusters delete rocket --num-nodes=2

helm repo add rocketchat-server https://rocketchat.github.io/helm-charts