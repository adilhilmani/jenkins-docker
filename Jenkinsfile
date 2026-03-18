pipeline {
    agent any

    stages {
        stage('Test Docker') {
            steps {
                sh 'whoami'
                sh 'ls -l /var/run/docker.sock || true'
                sh 'docker version'
                sh 'docker ps'
            }
        }
    }
}
