pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/niteshsharma99/jenkins-docker.git'
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
                bat 'docker rm -f my-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name my-container my-node-app'
            }
        }
    }
}