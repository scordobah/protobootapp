pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                build 'my_project'
                // script {
                //     // Usando Maven para construir el proyecto
                //     sh './mvnw clean package' // Para Unix/Linux
                //     // bat 'mvnw.cmd clean package' // Para Windows
                // }
            }
        }
        // stage('Test') {
        //     steps {
        //         script {
        //             // Ejecutar pruebas
        //             sh './mvnw test' // Para Unix/Linux
        //             // bat 'mvnw.cmd test' // Para Windows
        //         }
        //     }
        // }
        // stage('Archive Artifacts') {
        //     steps {
        //         archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        //     }
        // }
    }

    post {
        success {
            echo 'Build and Tests completed successfully!'
        }
        failure {
            echo 'Build or Tests failed.'
        }
    }
}