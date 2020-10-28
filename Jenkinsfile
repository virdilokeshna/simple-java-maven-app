pipeline{
    agent {
        docker{
            image 'maven'
            args '-v /root/.m2:/root/.m'
        }
    }

    stages{
        stage('build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}