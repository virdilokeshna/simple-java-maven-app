pipeline {
    agent any
   tools{
       sonar 'sonarqube'
   }
    /*agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }*/
    stages {
        stage('Build') {
            tools{
                maven 'maven'
            }
            /*tools {
                dockerTool 'docker'
            }*/
            steps {
                //sh 'docker --version'
                echo 'Build start'
                //sh 'mvn -B -DskipTests clean package'
                sh 'mvn compile'
            }
        }
        stage('scan') {
            
            steps {
                
                sh 'mvn sonar:sonar'
            }
        }
    }
}
