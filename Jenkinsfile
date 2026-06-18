pipeline {
    agent any

    tools {
        gradle 'Gradle8'
        jdk 'Java21'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Cipherun/gradleExt.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Skip tests
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'gradle run'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
