pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Wanted162/jenkins-webhook-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project..."
            }
        }
    }

    post {
        success {
            emailext(
                subject: "SUCCESS: Jenkins Job - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build succeeded! \nCheck console output at ${env.BUILD_URL}",
                to: "pisalpranit1@gmail.com"
            )
        }
        failure {
            emailext(
                subject: "FAILED: Jenkins Job - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build failed! \nCheck console output at ${env.BUILD_URL}",
                to: "pisalpranit1@gmail.com"
            )
        }
    }
}
