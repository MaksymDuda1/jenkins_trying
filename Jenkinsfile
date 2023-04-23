pipeline {
    agent any
    enviroment{
	dockerImage =''
	registry ='maksi123/lab1'
	}
    stages {
        stage('build image') {
            steps {
		script{
		   dockerImage = docker.build registry
		}
            }
        }
    }
}
 
