pipeline {
    agent any

    environment {
        IMAGE_NAME = "pradeep/jenkins-demo"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'git@github.com:08pradeep/my-first.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 $IMAGE_NAME'
            }
        }
    }
}
