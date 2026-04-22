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
                echo 'Installing dependencies (simulated)...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests (simulated)...'
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
