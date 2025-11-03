pipeline {
    agent any

    environment {
        IMAGE_NAME = "faiz-node-aws"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Faiz-official/aws-node-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    docker.image("${IMAGE_NAME}").run('-d -p 8080:8080')
                }
            }
        }
    }
}

