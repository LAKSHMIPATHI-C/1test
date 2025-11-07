pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git(branch: 'main', url: 'https://github.com/LAKSHMIPATHI-C/1test.git')
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML file...'
                bat '''
                if not exist build mkdir build
                echo ^<html^>^<body^>^<h1^>Hello Jenkins this is my first succesful job!^</h1^>^</body^>^</html^> > build\\index.html
                '''
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
        success {
            echo '✅ Build succeeded.'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
