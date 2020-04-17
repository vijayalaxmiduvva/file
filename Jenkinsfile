// Declarative pipeline
pipeline {
    agent any
    
    stages {
          
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
                sh "mvn tomcat:redeploy"
            }
        }
	    
    post {
           success {
               emailext (
                  to: '$DEFAULT_RECIPIENTS',
                  subject: "SUCCESS",
                  body: "SUCCESS!"
                )
            }
          failure {
	       emailext (
                  to: '$DEFAULT_RECIPIENTS',
                  subject: "FAILURE",
                  body: "FAILURE!"
                )
            }
        }
    }
} 
