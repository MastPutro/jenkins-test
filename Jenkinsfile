pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'frontend-jenkins'
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/MastPutro/jenkins-test.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8000:8000 $DOCKER_IMAGE'
            }
        }
    }
}
