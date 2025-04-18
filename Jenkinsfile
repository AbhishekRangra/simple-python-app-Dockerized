pipeline {
    agent any
    environment {
        DOCKER_HUB_REPO = 'abhishekrangra/pyabhi'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/AbhishekRangra/simple-python-app-Dockerized.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_HUB_REPO .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-credentials', url: '']) {
                    sh 'docker push $DOCKER_HUB_REPO'
                }
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 5000:5000 $DOCKER_HUB_REPO'
            }
        }
    }
}
