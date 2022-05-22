pipeline {
    agent any
    stages {
        stage('start') {
            steps {
                echo "hello world"
            }
        }
        stage('docker hub') {
            steps {
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t backend_user .'
                    sh 'docker tag backend_user 225702921/backend_user:v1'
                    sh 'docker push 225702921/backend_user:v1'
                }
            }
        }
    }
}