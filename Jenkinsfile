pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub_credentials' // replace with your Docker Hub credentials ID
        DOCKER_IMAGE_NAME = 'your-dockerhub-username/jenkins25' // replace with your Docker Hub username
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-github-username/your-repo-name.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    def app = docker.build(DOCKER_IMAGE_NAME)
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        app.push()
                    }
                }
            }
        }
    }
}
