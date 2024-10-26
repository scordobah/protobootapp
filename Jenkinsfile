pipeline {
    agent any

    tools {
        maven 'my_maven' // The name you configured in Global Tool Configuration
    }

    stages {
        stage('Code Build') {
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
            jacoco()
            junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [mavenConsole()]
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [checkStyle()]
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [pmdParser()]
            recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [spotBugs(useRankAsPriority: true)]
        }
        success {
            echo 'Build and Tests completed successfully!'
        }
        failure {
            echo 'Build or Tests failed.'
        }
    }
}