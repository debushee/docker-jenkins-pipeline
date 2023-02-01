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
                ssh -i "~/.ssh/id_rsa" jenkins@35.240.123.43 << EOF
                docker stop docker-jenkins-pipeline
                docker rm docker-jenkins-pipeline
                docker rmi docker-jenkins-pipeline
                docker run -d -p 80:5500 --name docker-jenkins-pipeline debushee/docker-jenkins-pipeline:latest
                ''' 
            }
        }
    }
}