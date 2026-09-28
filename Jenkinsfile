pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
               
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat 'pytest'
                //bat 'venv\\Scripts\\python -m pytest test_app.py'
            }
        }

        stage('Build') {
            steps {
                bat 'if not exist build mkdir build'
                bat 'copy app.py build\\'
                bat 'copy requirements.txt build\\'
            }
        }
    }
}
