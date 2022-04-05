## Exadel final project CI part

Work with Google Cloud Platform:
1. Create an account in Google Cloud Platform
2. Connect the Google CLI on the localhost with GCP account, run `gcloud init`, then sign in to GCP account, choose project and region
3. Create a new project and Service account for Github actions. Get project ID and JSON key-file, add them to Github secrets
4. Add Storage Admin role for service account 
5. Install the Google Cloud CLI according to official guide https://cloud.google.com/sdk/docs/install-sdk
6. Enable API for Cloud container registry `gcloud services enable containerregistry.googleapis.com`

Work with Github actions:
1. Create pipeline for building application and pushing it to Cloud container registry. The pipeline is /.github/workflows/Build_and_Push.yml

## Exadel final project CD part

Work with Google Cloud Platform:
1. Install the Kubectl `apt install kubectl`
2. Install Helm 3 for applying helm charts according to official guide https://helm.sh/docs/intro/install/
3. Enable required APIs `gcloud services enable container.googleapis.com`
4. Finally create Kubernetes cluster for deploying the project
`gcloud container clusters create rocket --num-nodes=5 --disk-size=15 --machine-type=e2-medium`
5. Create Bucket an cloud storage for backups

Work with Github actions:
1. Create pipeline for deploying Rocket-chat application. After checkout and authentication in GCP runs deployment from manifests files of two Kubernetes pods: Mongo database and Chat application. The pipeline is /.github/workflows/gcp.yml
2. Create pipeline for deploying metrics and logging. It consists of Prometheus+Grafana stack for metrics and EFK stack for logging. Each stack deploys in its own namespace. At first, add helm repos for each app, then deploy these apps with helm-charts. The pipeline is /.github/workflows/Prometheus and EFK.yml
3. Create pipeline for deploying Kasten app for backups. This application has been deployed with helm-chart too. The pipeline is /.github/workflows/kasten.yml

Post-installation steps:
1. Run Kasten app with port-forwarding `kubectl --namespace backup port-forward service/gateway 8080:8000`. The Kasten dashboard will be available at http://127.0.0.1:8080/k10/#/ 
2. Add Bucket for storage backups
3. Create backup policy for Rocket-chat application
