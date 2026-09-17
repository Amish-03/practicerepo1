pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout dev
            }
        }

        stage('Compile') {
            steps {
                bat '''mvn clean compile'''
            }
        }

        stage('Test') {
            steps {
                bat '''mvn test'''
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package -DskipTests'
            }
        }
    }

    post {
        success {
            echo 'Build, tests and packaging completed successfully!'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}