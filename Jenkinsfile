pipeline {
    agent any

    environment {
        DEPLOY_DIR = '/var/www/html'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Ritesh1914/static-website-hosting-EC2.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                    sudo rm -rf $DEPLOY_DIR/*
                    sudo cp -r ./* $DEPLOY_DIR/
                '''
            }
        }
    }

    post {
        success {
            echo 'Portfolio deployed successfully to Apache!'
        }
    }
}
