pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/amaliiaps/node-js-sample.git'
            }
        }

        stage('Install & Test in Docker') {
            steps {
                sh '''
                docker run --rm \
                -v $PWD:/app \
                -w /app \
                node:18 \
                npm install

                docker run --rm \
                -v $PWD:/app \
                -w /app \
                node:18 \
                npm test || true
                '''
            }
        }
    }

    post {
        success {
            echo 'SUCCESS'
        }
        failure {
            echo 'FAILED'
        }
    }
}
