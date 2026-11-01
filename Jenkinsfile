
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
                sh 'git --version'
                sh 'python3 --version'
            }
        }

        stage('Python Syntax Check') {
            steps {
                sh 'python3 -m py_compile program1.py'
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
