pipeline {
    agent any
    stages {
         stage("Pull Latest Image") {
            steps {   
                sh "docker pull amitkumarr99/selenium-docker"
            }
        } 
        stage("Start Grid") {
            steps {   
                sh "docker-compose up -d selenium-hub chrome"
            }
        }
	stage("Run Tests") {
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
