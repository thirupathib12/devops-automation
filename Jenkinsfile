pipeline {
    agent any
    tools{
        maven 'maven-3.8.1'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Java-Techie-jt/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t javatechie/devops-integration .'
                }
            }
        }
       
       }
}
