// Declarative pipeline
pipeline {
    agent any
    
    node {
    git credentialsId: 'a4280235-505b-4a86-88ee-3977b9b2ae15', url: 'https://github.com/vijayalaxmiduvva/file.git'
    }

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
                sh "mvn tomcat:deploy"
            }
        }
   }
}
