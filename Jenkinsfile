pipeline {
    agent any
   
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
                
                sh 'mvn sonar:sonar \
                    -Dsonar.projectkey=my-app \
                    -Dsonar.host.url=http://40.76.90.228 \ 
                    -Dsonar.login=dc89f8dv08920ff1fb37c8a9b0712c96c1a3a857'

            }
        }
    }
}
