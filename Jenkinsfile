pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Tools') {
            steps {
                bat 'git --version'
                bat 'python --version'
            }
        }

        stage('Python Syntax Check') {
            steps {
                bat 'python -m py_compile program1.py'
            }
        }

        stage('Build Complete') {
            steps {
                echo 'Jenkins pipeline completed successfully.'
            }
        }
    }

    post {
        success {
            echo 'Build passed.'
        }
        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}