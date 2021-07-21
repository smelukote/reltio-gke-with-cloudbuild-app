# model
# reltio-gke-with-cloufbuild
![image](https://user-images.githubusercontent.com/4884923/126421829-5fc3fa5a-7b6a-4728-aa93-8a3400d95c16.png)
Objectives
Create Git repositories in GitHub Repositories.
Create a container image with Cloud Build and store it in Container Registry.
Create a CI pipeline.
Create a CD pipeline.
Test the CI/CD pipeline.

Select or create a Cloud project.

Go to Manage Resources

Enable billing for your project.

Enable Billing

Open Cloud Shell to execute the commands listed in this tutorial. Cloud Shell is an interactive shell environment for Google Cloud that lets you manage your projects and resources from your web browser.

Go to Cloud Shell

If the gcloud config get-value project command does not return the ID of the project you selected, configure Cloud Shell to use your project.


gcloud config set project [PROJECT_ID]
In Cloud Shell, enable the required APIs.


gcloud services enable container.googleapis.com \
    cloudbuild.googleapis.com \
    sourcerepo.googleapis.com \
    containeranalysis.googleapis.com
In Cloud Shell, create a GKE cluster that you will use to deploy the sample application of this tutorial.


gcloud container clusters create hello-cloudbuild \
    --num-nodes 1 --zone us-central1-b
If you have never used Git in Cloud Shell, configure it with your name and email address. Git will use those to identify you as the author of the commits you will create in Cloud Shell.


git config --global user.email "[YOUR_EMAIL_ADDRESS]"
git config --global user.name "[YOUR_NAME]"
Run the gcloud credential helper. This will connect your Google Cloud user account to Cloud Source Repositories.


git config --global credential.helper gcloud.sh


Create GitHub Repository:

Git pull the repository and update cloudbuild.yaml with GKE cluster details.

gcloud builds submit .
----
---
e6309f: digest: sha256:d7323bbea61d10c0e05c446c12145045ec871acd6370e2216889d54460c9c552 size: 1995
DONE
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
ID                                    CREATE_TIME                DURATION  SOURCE                                                                                    IMAGES                                      STATUS
----
