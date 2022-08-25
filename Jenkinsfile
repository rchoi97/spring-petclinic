// https://www.liatrio.com/blog/building-with-docker-using-jenkins-pipelines

sAgentLabel = 'wsl2'

pipeline {
    agent {
        label sAgentLabel
    }
    stages {
        stage('Maven Install') {
            agent {
                docker {
                    image 'maven:3.5.0'
                }
            }
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t shanem/spring-petclinic:latest .'
            }
        }
    }
}
