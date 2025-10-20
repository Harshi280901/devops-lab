pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "sriharshini/devops-sample-app"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/devops-sample-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Docker Build & Push') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE).push()
                }
            }
        }

        stage('Deploy') {
            steps {
                sh './deploy.sh'
            }
        }
    }
}
