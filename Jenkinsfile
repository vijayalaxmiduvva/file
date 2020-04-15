// Declarative pipeline
pipeline {
    agent any
    
    stages {
        
        stage ('Git Checkout') {
            steps {
                git branch:'master'
                    credentialsId:'a4280235-505b-4a86-88ee-3977b9b2ae15' 
                    url:'https://github.com/vijayalaxmiduvva/file.git'
                sh "ls -lat"    
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
