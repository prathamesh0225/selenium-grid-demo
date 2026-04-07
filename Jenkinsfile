pipeline {
    agent any

    stages {
        // stage('Checkout') {
        //     steps {
        //         git 'https://github.com/prathamesh0225/selenium-grid-demo.git'
        //     }
        // }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Report') {
            steps {
                publishHTML([
    reportDir: 'reports',
    reportFiles: 'index.html',
    reportName: 'Extent Report',
    keepAll: true,
    alwaysLinkToLastBuild: true,
    allowMissing: true
])
            }
        }
    }
}
