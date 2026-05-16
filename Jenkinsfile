pipeline {

    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-management .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop student-container || true'
                sh 'docker rm student-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name student-container student-management'
            }
        }

    }
}