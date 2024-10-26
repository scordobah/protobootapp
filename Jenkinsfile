pipeline {
    agent any

    tools {
        maven 'my_maven' // The name you configured in Global Tool Configuration
    }

    stages {
        // stage('Checkout') {
        //     steps {
        //         checkout scm
        //     }
        // }
        stage('Build') {
            steps {
                script {
                    // Usando Maven para construir el proyecto
                    bat 'mvn compile test install package'
                }
            }
        }
    }

    post {
        stage('Code Coverage') {
            steps {
                jacoco()
            }
        }
        stage('JUnit Report') {
            junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
        }
        stage('Record compiler') {
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [mavenConsole()]
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [checkStyle()]
        }
        success {
            echo 'Build and Tests completed successfully!'
        }
        failure {
            echo 'Build or Tests failed.'
        }
    }
}