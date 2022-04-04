- gcloud services enable container.googleapis.com

- gcloud container clusters create rocket --num-nodes=4 --disk-size=15 --machine-type=e2-medium
- gcloud container clusters get-credentials rocket --zone=us-central1-a
- gcloud container clusters delete rocket


================================================


- helm repo add rocketchat-server https://rocketchat.github.io/helm-charts
- kubectl port-forward rocketchat-1648421186-rocketchat-798fdbd6c5-jrg6x 7777:80
- kubectl expose deployment namedeploment --type=LoadBalancer --port 80

gcr.io/hale-carport-345014/rocket-chat@sha256:4882088613f6f0d77325e09b7027ecabbb37fbb1108d9803d0a50b4029bdddb6
kubectl create namespace rocketteam


echo "bW9uZ29kYjovL3JvY2tldGNoYXQ6dGVzdFBBU1NAbXlyb2NrZXQtbW9uZ29kYi1oZWFkbGVzczoyNzAxNy9yb2NrZXRjaGF0P3JlcGxpY2FTZXQ9cnMw" | base64 --decode

kubectl -n rocketteam apply -f ./manifests/rocketchat/ -f ./manifests/mongodb/
kubectl -n rocketteam delete -f ./manifests/rocketchat/ -f ./manifests/mongodb/


helm repo add bitnami https://charts.bitnami.com/bitnami
helm upgrade --create-namespace -i metrics prometheus bitnami/kube-prometheus
helm upgrade -i -n metrics grafana bitnami/grafana --set admin.password=admin
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
helm upgrade -i -n metrics loki grafana/loki

helm search repo
11455 #grafana id dashboard
7249 
315
8860
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm upgrade -i --create-namespace kube-prometheus-stack -n metrics --set grafana.adminPassword=admin prometheus-community/kube-prometheus-stack --version 34.7.1


helm upgrade -i -n metrics elastic bitnami/elasticsearch --set global.kibanaEnabled=true
helm repo add kokuwa https://kokuwaio.github.io/helm-charts
helm upgrade -i -n metrics fluentd kokuwa/fluentd-elasticsearch
helm pull <chart-name> --untar


helm repo add fluent https://fluent.github.io/helm-charts
helm install -n metrics fluent-bit fluent/fluent-bit
kubectl create -f https://raw.githubusercontent.com/fluent/fluent-bit-kubernetes-logging/master/output/elasticsearch/fluent-bit-ds.yaml

helm upgrade --install -n metrics loki grafana/loki

12019
15141
13639

14055
Get this dashboard:
13198
13639