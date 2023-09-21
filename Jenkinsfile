pipeline {
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage('Git checkout'){
            steps{
                echo "Pull Code From GitHub..."
                git credentialsId: 'new_git_Cre', url: 'https://github.com/Thanhlam43k4/Complete_Jenkins_CI.git'
            }
        }
        stage('Test'){
            steps{
                echo "Testing....."
                sh 'mvn --version'
                sh 'java --version'    
                sh 'mvn clean package'
            }
        }
        stage('Packaging/Pushing image'){
            steps{
                    sh 'ls -ltr'
                    withDockerRegistry(credentialsId: 'dockerhub_Cre_new', url: 'https://index.docker.io/v1/') {
                        sh 'docker build -t thanhlam2k4/spring_boot_app:6.0 .'
                        sh 'docker push thanhlam2k4/spring_boot_app:6.0'

                    }
                         
                }
        }
        stage('Deploying to Kubernetes!!'){
            steps{
                script{
                    echo 'Deploying to k8s .....'
                }
            }

        }
            
        
    }
    // post{
    //     // Clean after build
    //     always{
    //         cleanWs()
    //     }
    // }
}
