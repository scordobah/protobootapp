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
        always {
            junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
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