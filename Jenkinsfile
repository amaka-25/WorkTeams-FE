pipeline {
    agent any
    tools {
        nodejs 'nodejs' // Assumes nodejs plugin with 'Node24' installation configured
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/amaka-25/WorkTeams-FE.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
