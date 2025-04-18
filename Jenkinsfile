pipeline {
    agent any
    environment {
<<<<<<< HEAD
        DOCKER_HUB_REPO = 'abhishekrangra/pyabhi'
=======
        DOCKER_HUB_REPO = 'abhishekrangra/pythonapp'
>>>>>>> 9522464c5d3f18e2bf97b96eb403a5180fba5b44
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
<<<<<<< HEAD
                withDockerRegistry([credentialsId: 'dockerhub-credentials', url: '']) {
=======
                withDockerRegistry([credentialsId: 'dockerhub', url: '']) {
>>>>>>> 9522464c5d3f18e2bf97b96eb403a5180fba5b44
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
