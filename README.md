## Jenkins CI/CD with Docker

##  Step 1: Run Jenkins in Docker
docker run --user root -p 8080:8080 -p 50000:50000 --restart=on-failure -d -v /var/run/docker.sock:/var/run/docker.sock -v jenkins_home:/var/jenkins_home --name jenkins-docker jenkins/jenkins:lts-jdk17

## Step 2: Access Jenkins Container
docker exec -it jenkins-docker bash

##  Step 3: Install Docker Inside Jenkins Container
apt update && apt install -y docker.io

## Step 4: Create Docker Hub Access Token
Go to Docker Hub Account Settings
Create a Personal Access Token with:
Read-Write-Delete permissions

## Step 5: Add Credentials in Jenkins Dashboard
Path to Add Credentials:
Dashboard → Manage Jenkins → Credentials → System → Global credentials (unrestricted)
Kind: Username with password
Username: Docker Hub username
Password: Docker Hub access token
## Configure the Pipeline:
![Configuration-Pipeline](https://github.com/user-attachments/assets/a32833df-0701-444b-9013-cb7592a919d6)

## Final Output After Successful Pipeline Execution:
![Final Output](https://github.com/user-attachments/assets/710feeb2-0a31-4ac9-bee7-6c8a25d4e25a)
