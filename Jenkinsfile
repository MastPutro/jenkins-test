pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'nama_image_laravel'
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/kamu/laravel-project.git'
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
