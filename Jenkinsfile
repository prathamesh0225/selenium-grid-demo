pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/prathamesh0225/selenium-grid-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Report') {
            steps {
                publishHTML([
                    reportDir: 'reports',
                    reportFiles: 'extent-report.html',
                    reportName: 'Test Report'
                ])
            }
        }
    }
}
