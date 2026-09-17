pipeline {
    agent any
C:\ProgramData\Jenkins\.jenkins\workspace\LoginServiceTesting
    stages {

        stage('Compile') {
            steps {
                bat '''
                cd C:\ProgramData\Jenkins\.jenkins\workspace\LoginServiceTesting\configserver
                mvnw.cmd clean compile'''
            }
        }

        stage('Test') {
            steps {
                bat '''
                cd C:\ProgramData\Jenkins\.jenkins\workspace\LoginServiceTesting\configserver
                mvnw.cmd test'''
            }
        }

        stage('Package') {
            steps {
                bat '''
                cd C:\ProgramData\Jenkins\.jenkins\workspace\LoginServiceTesting\configserver
                mvnw.cmd package -DskipTests'''
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
