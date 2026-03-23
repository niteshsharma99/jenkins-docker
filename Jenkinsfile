pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/niteshsharma99/jenkins-docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("my-node-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker rm -f my-container || true'
                    sh 'docker run -d -p 3000:3000 --name my-container my-node-app'
                }
            }
        }
    }
}