
pipeline {


    agent any

    environment {
        IMAGE_NAME = "flask-app-docker-jenkins"
        CONTAINER_NAME = "flask-app-docker-jenkins-container"
        DOCKER = "docker"
        REPO_URL = "https://github.com/Yomi-coder/Flask-App-with-Docker-and-Jenkins-Pipeline.git"
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: "$REPO_URL"
            }
        }
    

        stage('Check Docker') {
            steps {
                sh '$DOCKER --version'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '$DOCKER build -t $IMAGE_NAME .'
            }
        }

    

        stage('Stop Old Container') {
            steps {
                sh '''
                $DOCKER stop $CONTAINER_NAME || true
                $DOCKER rm $CONTAINER_NAME || true
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '$DOCKER run -d -p 8085:5000 --name $CONTAINER_NAME $IMAGE_NAME'
            }
        }

    }

}


