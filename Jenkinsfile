pipeline {
    agent any
    stages {
        stage('Docker version') {
            steps {
                sh '''
                    echo $USER
                    docker version
                '''
            }
        }
        stage('Checkout') {
            steps{
                git branch: 'main',
                    url: 'git@github.com:MaksymDuda1/jenkins_trying.git'        
                }
        }
        stage('Build docker image') {
            steps {
                sh '''
                    docker build -t maksi123/lab1 .
                '''
            }
            
        }
  
    }
}
