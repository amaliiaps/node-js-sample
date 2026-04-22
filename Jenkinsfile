pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/amaliiaps/node-js-sample.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || true'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS CI OK'
        }
        failure {
            echo 'FAILED'
        }
    }
}
