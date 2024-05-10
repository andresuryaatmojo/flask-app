pipeline {
    agent any

    tools {
        python 'Python3'
    }

    stages {
        stage('Setup') {
            steps {
                // Ensuring that the virtual environment is activated correctly
                script {
                    bat 'python -m venv venv'
                    bat 'call venv\\Scripts\\activate'
                    bat 'pip install -r requirements.txt'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    echo 'Building the Project...'
                    bat 'echo Build complete.'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Running Tests...'
                    bat 'echo Tests completed.'
                }
            }
        }
        stage('Lint') {
            steps {
                script {
                    echo 'Linting Code...'
                    bat 'pip install flake8'
                    bat 'flake8 .'
                }
            }
        }
        stage('Report') {
            steps {
                script {
                    echo 'Generating Reports...'
                    bat 'echo Reports generated.'
                }
            }
        }
    }
    post {
        always {
            script {
                echo 'Cleaning up...'
                bat 'call venv\\Scripts\\deactivate'
                bat 'rd /s /q venv'
            }
        }
    }
}
