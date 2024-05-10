pipeline {
    agent any

    tools {
        // Ganti 'python' dengan identifier yang tepat
        'jenkins.plugins.shiningpanda.tools.PythonInstallation' 'Python3'
    }

    stages {
        stage('Setup') {
            steps {
                sh 'python -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the Project...'
                sh 'echo "Build complete."'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'echo "Tests completed."'
            }
        }
        stage('Lint') {
            steps {
                echo 'Linting Code...'
                sh 'pip install flake8'
                sh 'flake8 .'
            }
        }
        stage('Report') {
            steps {
                echo 'Generating Reports...'
                sh 'echo "Reports generated."'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            sh 'deactivate'
            sh 'rm -rf venv'
        }
    }
}
