pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop nodeapp || true'
                sh 'docker rm nodeapp || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name nodeapp node-app'
            }
        }
    }
}
