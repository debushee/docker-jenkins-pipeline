pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t docker-jenkins-pipeline:latest .
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
        stage('Deploy') {
            steps {
                sh '''#!/bin/bash
                source venv/bin/activate
                JENKINS_NODE_COOKIE=nokill gunicorn --bind=0.0.0.0:8001 hangman:app -D'''
            }
        }
        stage('Test') {
            steps {
                sh 'curl localhost:8001'
            }
        }
        stage('Clean up') {
            steps {
                sh 'pkill gunicorn'
            }
        }
    }
}