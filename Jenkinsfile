pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerCredentials') {
                        sh "docker build -t sumakallem/emailservice_shop:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'DockerCredentials') {
                        sh "docker push sumakallem/emailservice_shop:latest"
                    }
                }
            }
        }
    }
}
