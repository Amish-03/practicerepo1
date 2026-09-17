pipeline {
    agent any

    stages {

        stage('Compile') {
            steps {
                dir('configserver') {
                    bat 'mvnw.cmd clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                dir('configserver') {
                    bat 'mvnw.cmd test'
                }
            }
        }

        stage('Package') {
            steps {
                dir('configserver') {
                    bat 'mvnw.cmd package -DskipTests'
                }
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

