pipeline{
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
           /* tools {
                maven 'maven'
            }*/
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
       /* stage('test') {
        steps {
            sh 'mvn test'
            }
            post {
                always {
                // One or more steps need to be included within each condition's block.
                }
            }

        }*/

    }   
}
