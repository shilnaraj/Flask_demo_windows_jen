pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'python -m venv venv'
                bat 'venv\\Scripts\\pip install -r requirement.txt'
            }
        }

        stage('Test') {
            steps {
                bat 'venv\\Scripts\\python -m pytest test_app.py'
            }
        }

        stage('Build') {
            steps {
                bat 'if not exist build mkdir build'
                bat 'copy app.py build\\'
                bat 'copy requirement.txt build\\'
            }
        }
    }
}