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
                sh '''
                docker run --rm -v $PWD:/app -w /app node:18 npm install
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                docker run --rm -v $PWD:/app -w /app node:18 npm test || true
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                docker run --rm -v $PWD:/app -w /app node:18 npm run build || true
                '''
            }
        }
    }

    post {
        success {
            echo 'SUCCESS CI PIPELINE'
        }
        failure {
            echo 'FAILED'
        }
    }
}
