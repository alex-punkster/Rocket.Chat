## Exadel final project CD part

Work with Google Cloud Platform:
1. Create an account in Google Cloud Platform
2. Create a new project and Service account for Github actions. Get project ID and JSON key-file, add them to Github secrets
3. Install the Google Cloud CLI according to official guide https://cloud.google.com/sdk/docs/install-sdk
4. Install the Kubectl `apt install kubectl`
5. Install Helm 3 for applying helm charts according to official gude https://helm.sh/docs/intro/install/
6. Connect the Google CLI on the localhost with GCP account, run `gcloud init`, then sign in to GCP account, choose project and region
7. Enable required APIs `gcloud services enable container.googleapis.com`
8. Finally create Kubernetes cluster for deploying the project
