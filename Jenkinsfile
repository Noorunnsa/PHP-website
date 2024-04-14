pipeline {
    agent any

    environment {
        DOCKER_REGISTRY = 'docker.io'
        DOCKER_USERNAME = credentials('docker-hub-username')
        DOCKER_PASSWORD = credentials('docker-hub-password')
        DOCKER_IMAGE = 'Myrepository:latest'
        DOCKERFILE_PATH = './website/dockerfile'
        CONTAINER_NAME = 'php-container'
        PORT_MAPPING = '8080:80' 
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${DOCKER_IMAGE} -f ${DOCKERFILE_PATH} ."
                }
            }
        }

        stage('Login to Docker Registry') {
            steps {
                script {
                    sh "docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD} ${DOCKER_REGISTRY}"
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    sh "docker push ${DOCKER_IMAGE}"
                }
            }
        }

        stage('Start Docker Container') {
            steps {
                script {
                    sh "docker run -d --name ${CONTAINER_NAME} -p ${PORT_MAPPING} ${DOCKER_IMAGE}"
                }
            }
        }
    }

    post {
        success {
            echo 'Docker image build, push, and container start successful!'
        }
        failure {
            echo 'Docker image build, push, or container start failed!'
        }
    }
}
