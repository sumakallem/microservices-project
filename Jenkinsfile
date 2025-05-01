pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerCredentials') {
                        sh 'docker build -t sumakallem/paymentservice_shop:latest .'
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'DockerCredentials') {
                        sh 'docker push sumakallem/paymentservice_shop:latest'
                    }
                }
            }
        }
    }
}
