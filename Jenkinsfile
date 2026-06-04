pipeline {
    agent any

    stages {

        stage('Install') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t python-ci-cd .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5000:5000 python-ci-cd'
            }
        }
    }
}
