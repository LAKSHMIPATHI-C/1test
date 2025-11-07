pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/LAKSHMIPATHI-C/1test.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML file...'
                bat 'mkdir build'
                bat 'copy index.html build\\index.html'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'build/**', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
