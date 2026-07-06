pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                echo 'Build completed successfully!'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                pkill -f "node app.js" || true
                nohup node app.js > app.log 2>&1 &
                '''
            }
        }
    }
}
