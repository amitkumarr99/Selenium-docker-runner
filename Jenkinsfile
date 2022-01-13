pipeline {
    agent any
    stages {
        stage('Run Tests') {
            steps {
                
                sh "docker-compose up"
            }
        }
        stage('Bring Grid Down') {
            steps {
                sh "docker-compose down"
            }
        }
        
    }
}
