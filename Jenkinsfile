pipeline {
    agent any
    
    stages {
        stage('build image') {
            steps {
		script{
		   docker build -t maksi123/lab1 .
		   }
		}
            }
        }
    }
}
 
