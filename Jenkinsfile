// Declarative pipeline
pipeline {
    agent any
    
    stages {
        
        stage ('Git Checkout') {
            steps {
                git branch: 'Master'
                    credentialsId: 
                    url:
            }           
        }   
        stage('Compile Stage') {
            steps {
                sh "mvn clean compile"
            }
        }
        stage('Package') {
            steps {
                sh "mvn package"
            }
        }
        stage('Deploy') {
            steps {
                sh "mvn tomcat:deploy"
            }
        }
   }
}
