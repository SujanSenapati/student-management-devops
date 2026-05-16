pipeline {

    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t student-management .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop student-container || exit 0'
                bat 'docker rm student-container || exit 0'
            }
        }

        stage('Run New Container') {
            steps {
                bat 'docker run -d -p 5000:5000 --name student-container student-management'
            }
        }

    }
}