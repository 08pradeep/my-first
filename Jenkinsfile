pipeline {
    agent any

    environment {
        IMAGE_NAME = "pradeep/jenkins-demo"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f myapp || true'
                sh 'docker run -d -p 5000:5000 --name myapp $IMAGE_NAME'
            }
        }
    }
}
