- gcloud services enable container.googleapis.com

- gcloud container clusters create rocket --num-nodes=2 --disk-size=15 --machine-type=e2-medium
- gcloud container clusters get-credentials rocket
- gcloud container clusters delete rocket


================================================


- helm repo add rocketchat-server https://rocketchat.github.io/helm-charts
- kubectl port-forward rocketchat-1648421186-rocketchat-798fdbd6c5-jrg6x 7777:80
- kubectl expose deployment namedeploment --type=LoadBalancer --port 80

gcr.io/hale-carport-345014/rocket-chat@sha256:4882088613f6f0d77325e09b7027ecabbb37fbb1108d9803d0a50b4029bdddb6
kubectl create namespace <namespace-name>
kubectl -n rocketchat create -f rocket-chat.yaml

echo "bW9uZ29kYjovL3JvY2tldGNoYXQ6dGVzdFBBU1NAbXlyb2NrZXQtbW9uZ29kYi1oZWFkbGVzczoyNzAxNy9yb2NrZXRjaGF0P3JlcGxpY2FTZXQ9cnMw" | base64 --decode

kubectl -n dimon apply -f ./manifests/rocketchat/ -f ./manifests/mongodb/
kubectl -n dimon delete -f ./manifests/rocketchat/ -f ./manifests/mongodb/


