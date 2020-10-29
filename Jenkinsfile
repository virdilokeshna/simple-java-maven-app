pipeline {
    /*agent any*/
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            /*tools{
                maven 'maven'
            }*/
            steps {
                echo 'Build start'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
