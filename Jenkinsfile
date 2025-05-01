pipeline {
    agent any
    stages {
        stage('Kubernetes deployment') {
            steps {
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'kubernetes_token', namespace: 'myapps', serverUrl: 'https://9EE639D8927C5469A8189F4F62919DE9.gr7.us-east-1.eks.amazonaws.com']]) {
                        sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        stage('Verify Deployment'){
            steps{
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'kubernetes_token', namespace: 'myapps', serverUrl: 'https://9EE639D8927C5469A8189F4F62919DE9.gr7.us-east-1.eks.amazonaws.com']]) {
                        sh "kubectl get svc -n myapps"
				}
            }
        }
    }
}
