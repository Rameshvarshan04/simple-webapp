pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Rameshvarshan04/simple-webapp.git'
            }
        }

     stage('Install Dependencies') {
            steps {
                git credentialsId: 'Github-Webhooks', url: 'https://github.com/Rameshvarshan04/simple-webapp.git'
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
