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
                sh 'npm build'
                sh 'npm build'
                sh 'sudo rm -r /var/www/html/'
                sh 'sudo cp -r /root/reactapp/build/* /var/www/html/'
            }
        }
    }
}