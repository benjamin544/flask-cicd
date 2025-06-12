pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "benyaminlaz/flask-cicd-app"
        DOCKERHUB_CREDENTIALS = "dockerhub-creds"
    }

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('', "${DOCKERHUB_CREDENTIALS}") {
                        docker.image("${DOCKER_IMAGE}").push("latest")
                    }
                }
            }
        }
    }
}
