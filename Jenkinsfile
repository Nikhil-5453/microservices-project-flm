pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-creds') {
                        sh "docker build -t nikhil74/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-creds') {
                        sh "docker push nikhil74/checkoutservice:latest "
                    }
                }
            }
        }
    }
}
