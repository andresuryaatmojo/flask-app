pipeline {
    agent any

    tools {
        python 'Python3'
    }

    stages {
        stage('Setup') {
            steps {
                bat 'python -m venv venv'
                bat 'venv\\Scripts\\activate'
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the Project...'
                bat 'echo Build complete.'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests...'
                bat 'echo Tests completed.'
            }
        }
        stage('Lint') {
            steps {
                echo 'Linting Code...'
                bat 'pip install flake8'
                bat 'flake8 .'
            }
        }
        stage('Report') {
            steps {
                echo 'Generating Reports...'
                bat 'echo Reports generated.'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            bat 'deactivate'
            bat 'rd /s /q venv'
        }
    }
}
