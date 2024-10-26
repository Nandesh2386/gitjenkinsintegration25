pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = '7eb9a6a1-0688-4931-beab-ddc25bebd485' // replace with your Docker Hub credentials ID
        DOCKER_IMAGE_NAME = 'nandesh25/jenkins25' // replace with your Docker Hub username
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Nandesh2386/gitjenkinsintegration25.git'
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
git branch: 'main',
    url: 'https://github.com/Nandesh2386/gitjenkinsintegration25.git',
    credentialsId: '7eb9a6a1-0688-4931-beab-ddc25bebd485' // Replace with your actual credentials ID
