pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Pull the latest code from the repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Example build command
                echo 'Building the application...'
                sh './gradlew build' // Replace with your build command
            }
        }
        stage('Test') {
            steps {
                // Run tests
                echo 'Running tests...'
                sh './gradlew test' // Replace with your test command
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the application
                echo 'Deploying the application...'
                sh './deploy.sh' // Replace with your deployment command
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            cleanWs() // Clean workspace after the build
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for details.'
        }
    }
}
