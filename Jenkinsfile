pipeline {
    agent any
   
    stages {
      
       
        stage ('Run Tests') {
            steps {
                bat 'docker ps -a' // Remplacez ceci par vos tests réels si nécessaire
            }
        }
        stage ('Run Docker Compose') {
            steps {
                bat 'docker-compose up -d'
            }
        }
    }
    post {
        success {
            slackSend channel: '#projetdevops', message: 'Build réussi'
        }
        failure {
            slackSend channel: '#projetdevops', message: 'Build echoue'
        }
    }
}
