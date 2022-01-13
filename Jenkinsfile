pipeline {
    agent any
    stages {
        stage('Start Grid') {
            steps {   
                sh "docker-compose up -d selenium-hub chrome firefox"
            }
        }
	stage('Run Tests') {
            steps {   
                sh "docker-compose up  smoke-suite regression-suite"
            }
        }
	}	
	post{
	    always{
		    archiveArtifacts artifacts: 'output/**'  
            sh "docker-compose down"    
            }
		}
    }
