

-----Complete CI process with Jenkins and some tools------

+ SonarQube: analysis of code to detect bugs and code smells on 29 programming language.
+ Jenkins: continous integration/continous delivery automation software Devops written in Java
+ Docker: open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.
+ Kubernetes: open-source system for automating deployment, scaling, and management of containerized applications.
+DockerHub: is the world's largestlibrary and community for container images.

Prequesites:
+ Install docker and minikube in Local Machine.
+ Containerized Jenkins Image and SonarQubeScanner.
+ Clone this Repo in your Local Machine.
+ Integration Jenkins with Docker.
+ Install Docker and Maven tools for build to Docker Hub .
+ Dowload kubectl for kubernetes command line.

Proceeding:
1.Continuous Integration and deploy images in Dockerhub.
- Open your jenkins web (http://localhost:8081 in my case normally is http://localhost:8080)
  
- Make Credentials for Jenkins Pipeline:
  +  In jenkins Dashboard ->> Manage Jenkins ->> Security ->> Credentials:
  +  Click to Add Credentials and add your Credentials of dockerhub account and GitHub account
     in my case are new_git_Cre(GitHub Credentials) and dockerhub_Cre_new(dockerhub Credentials)   
  +  Then in Jenkinsfile you change the credentialsId of GitHub and Dockerregistry.
    
- Create a new Jobs and use Pipeline item
  + Scroll down to Pipeline. You have two options
                              -Pipeline Script (Copy Jenkinsfile in your updated repo in this space)
                              -Pipeline Script from SCM(If you have GitHub account and Push your code in this)
    
- Then Click ->> Apply ->> Save

-Finished you can build project now

2.Deploy application in k8s locally

- Command(To boostrapp Kubernetes cluster in Minikube):
  
        minikube start

- And Turn on the terminal with directory to your project repo:

      cd /Complete_Jenkins_CI

- Check your deployments and pods: 

      kubectl get pods

      kubectl get deploy
  
-And deploy your image from dockerhub:

      docker pull (your_dockerhub_id)/spring_boot_app:6.0

      kubectl apply -f deploymentservice.yaml

-And check your service and API:

      minikube service app-service

      

>>>You can see your web application.Thank you and see you in next post!!!!!

Author:Nguyen Thanh Lam-UETK2K67


