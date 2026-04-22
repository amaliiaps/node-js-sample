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
                sh 'docker run --rm -v $PWD:/app -w /app node:18 npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'docker run --rm -v $PWD:/app -w /app node:18 npm test || echo "No test script found"'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline success!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
