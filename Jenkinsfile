pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code already checked out by Jenkins.'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'npm start'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }

        success {
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}