pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'git branch: 'main', url: 'https://github.com/LAKSHMIPATHI-C/1test.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building HTML file...'
                bat 'if not exist build mkdir build'
            }
        }
        stage('Archive Artifact') {
            steps {
                echo 'Archiving build output...'
                archiveArtifacts artifacts: '**/build/**', fingerprint: true
            }
        }
    }
    post {
        failure {
            echo '❌ Build failed.'
        }
        success {
            echo '✅ Build succeeded.'
        }
    }
}
