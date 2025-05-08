pipeline {
    agent any
    tools {
        nodejs 'NodeJs' // Assumes NodeJs plugin with 'Node24' installation configured
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
}
