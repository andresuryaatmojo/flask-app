pipeline {
    agent any

    tools {
        // Memastikan Python tersedia di agen build
        python 'Python3'
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
                // Simulasi build, misal kompilasi assets atau database migration
                sh 'echo "Build complete."'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests...'
                // Anda perlu memiliki skrip untuk menjalankan test di sini
                sh 'echo "Tests completed."'
            }
        }
        stage('Lint') {
            steps {
                echo 'Linting Code...'
                // Jalankan linter, asumsikan Anda menggunakan flake8 atau sejenisnya
                sh 'pip install flake8'
                sh 'flake8 .'
            }
        }
        stage('Report') {
            steps {
                echo 'Generating Reports...'
                // Simulasikan pembuatan laporan, misalnya menghasilkan laporan test coverage
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
