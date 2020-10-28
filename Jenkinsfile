pipeline {
    agent any
    stages {
        stage('Build') {
            tools{
                maven 'maven'
            }
            steps {
                echo 'Build start'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
