Nguyen Thanh Lam-UETK2K67

-----Complete CI process with Jenkins and some tools------

+ SonarQube: analysis of code to detect bugs and code smells on 29 programming language.
+ Jenkins: continous integration/continous delivery automation software Devops written in Java
+ Docker: open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.
+ Kubernetes: open-source system for automating deployment, scaling, and management of containerized applications.
+DockerHub: is the world's largestlibrary and community for container images.

Prequesites:
+ Install docker and minikube in Local Machine.
+ Containerized Jenkins Image and SonarQubeScanner
+ Clone this Repo in your Local Machine
+ Integration Jenkins with Docker
+ Install Docker and Maven tools for build to Docker Hub 


Proceeding:
- Open your jenkins web (http://localhost:8081 in my case normally is http://localhost:8080)
- Make Credentials for Jenkins Pipeline:
  +  In jenkins Dashboard ->> Manage Jenkins ->> Security ->> Credentials:
  +  Click to Add Credentials and add your Credentials of dockerhub account and GitHub account
     in my case are new_git_Cre(GitHub Credentials) and dockerhub_Cre_new(dockerhub Credentials)   
  +  Then in Jenkinsfile you change the credentialsId of GitHub and Dockerregistry.
- Create a new Jobs and use Pipeline item
-



