pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Ritesh1914/static-website-hosting-EC2.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                    sudo rm -rf /var/www/html/*
                    sudo cp -r * /var/www/html/
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
