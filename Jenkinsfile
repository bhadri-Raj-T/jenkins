pipeline {
    agent any

    environment {
        DOCKER = '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe"'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh '%DOCKER% build -t python-app .'
            }
        }

        stage('Run Tests Inside Docker') {
            steps {
                sh '%DOCKER% run python-app pytest'
            }
        }

        stage('Run Application') {
            steps {
                sh '%DOCKER% run --rm python-app'
            }
        }
    }
}


