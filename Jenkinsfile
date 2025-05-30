pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                expression { env.CHANGE_ID != null }
            }
            steps {
                echo "🔧 Building Pull Request #${env.CHANGE_ID}"
                echo "Source: ${env.CHANGE_BRANCH} → Target: ${env.CHANGE_TARGET}"
                bat 'echo "Simulating build..."'
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
        always {
            echo '📌 Build finished.'
        }
    }
}
