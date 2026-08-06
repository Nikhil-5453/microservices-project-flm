pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8s-creds', namespace: 'webapps', serverUrl: 'https://C891749C58AD0A6EB0CA6820261B7291.yl4.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8s-creds', namespace: 'webapps', serverUrl: 'https://C891749C58AD0A6EB0CA6820261B7291.yl4.ap-south-1.eks.amazonaws.coms']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
