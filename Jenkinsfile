pipeline {
  agent any
  
  environment {
    registry = "docker.io"
    registryCredential = '1'
    dockerImage = ''
    dockerfile = 'Dockerfile'
    imageName = 'maksi123/lab1'
    imageTag = 'latest'
    gitRepo = 'https://github.com/MaksymDuda1/jenkins_trying.git'
  }
  
  stages {
    stage('Build Docker Image') {
      steps {
        script {
          // Login to Docker Hub
          withCredentials([usernamePassword(credentialsId: "${registryCredential}", passwordVariable: 'password', usernameVariable: 'username')]) {
            sh "docker login -u ${username} -p ${password} ${registry}"
          }
          
          // Clone Git repository
          sh "git clone ${gitRepo}"
          
          // Build Docker image
          dockerImage = docker.build("${registry}/${imageName}:${imageTag}", "--file ${dockerfile} ./jenkins_trying")
        }
      }
    }
    
    stage('Push Docker Image') {
      steps {
        script {
          // Push Docker image to Docker Hub
          dockerImage.push()
        }
      }
    }
  }
}

