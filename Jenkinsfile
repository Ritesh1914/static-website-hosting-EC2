pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/Ritesh1914/static-website-hosting-EC2.git'
    }

    triggers {
        githubPush() // ✅ Enables GitHub webhook triggering
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: "${REPO_URL}"
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                    echo "Clearing old site files..."
                    sudo rm -rf /var/www/html/*
                    echo "Copying new files..."
                    sudo cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo 'Portfolio deployed successfully to Apache!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
