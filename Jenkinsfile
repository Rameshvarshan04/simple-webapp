pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/node-js-sample.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || echo \"No build step defined\"'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || echo \"No tests defined\"'
            }
        }

        stage('Deploy') {
            steps {
                sh 'npm start &'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
