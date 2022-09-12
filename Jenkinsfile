pipeline {
    agent {
        any {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Deliver') {
            steps {
                sh 'npm run build'
                sh 'sudo rm -r /var/www/html'
                sh 'sudo mkdir /var/www/html'
                sh 'sudo scp -r ${WORKSPACE}/build/* /var/www/html/'
            }
        }
    }
}