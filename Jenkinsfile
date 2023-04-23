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
        stage('Build docker image') {
            steps {
                sh '''
                    docker build -t maksi123/jenkins_trying .
                '''
            }
            
        }
        stage('docker login'){
            steps{
                withCredentials([usernamePassword(credentialsId: 'new_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')])  {
            sh"""
            docker login -u $USERNAME -p $PASSWORD
            """
                }
            }
        }
        
        stage('Push docker image to DockerHub') {
            steps {
                    sh '''
                        docker push maksi123/jenkins_trying
                    '''
                    
                }
            }
        }
}
