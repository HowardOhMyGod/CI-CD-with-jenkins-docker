# CI-CD-with-jenkins-docker
## Introduction
I have set up two Ubuntu 16.04 VMs on Azure, one is for Jenkins, the other is for web app production. They both installed docker engine. Docker for jenkins server is used to create a safe and isolated unit testing enviroment from the host for web app. The production server uses docker to run service and enbrace continous deployment.
This article assumes your have basic knowledge of docker and bash script.

## Wrokflow
We will create the following workflow
- Create Webhook on Github to trigeer Jenkins’ build process.
- Jenkins clone project repo.
- Jenkins build docker image for unit test.
- After testing, Jenkins remove test image and use Publish over SSH plugin to send workspace folder and executes build script on production server.
- Production build new docker image and run immediately.

## Tutorials on Medium
[CI / CD Workflow with Docker and Jenkins on Azure](https://medium.com/@howard036060006/ci-cd-workflow-with-docker-and-jenkins-on-azure-cloud-db200d6e8b12)

[CI / CD with Jenkins and Docker on Azure — Test and Deploy Node.js Application](https://medium.com/@howard036060006/ci-cd-with-jenkins-and-docker-on-azure-test-and-deploy-node-js-application-b1b218d679fb)
