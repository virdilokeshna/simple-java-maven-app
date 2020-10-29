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
            tools{
                sonar 'sonarqube'
            }
            steps {
                
                sh 'mvn sonar:sonar \
                    -Dsonar.host.url=http://sonarqubeprac.eastus2.cloudapp.azure.com:9000 \
                    -Dsonar.login=01bdceba9b6d1affb894339a049fec80be690eec'

            }
        }
    }
}
