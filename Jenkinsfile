pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t debushee/docker-jenkins-pipeline:latest .
                '''
            }   
        }
        stage('Push') {
            steps {
                sh '''
                docker push debushee/docker-jenkins-pipeline:latest
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                ''' 
            }
        }
    }
}