pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build image') {
            steps {
                sh 'docker build -t mon-site-nginx:latest .'
            }
        }

        stage('Deploy container') {
            steps {
                sh '''
                    docker rm -f nginx-site || true
                    docker run -d \
                      --name nginx-site \
                      -p 9200:80 \
                      mon-site-nginx:latest
                '''
            }
        }
    }
}
