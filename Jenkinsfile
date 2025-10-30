pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps{
            git (
                url: 'https://github.com/lijokuriala/java-standalone-application.git',
                branch: 'main'
                 )
            }
        }
        stage('Build') {
            steps {
                mvn clean install
            }
        }
        //stage('Run Application') {
            // write your logic here
        //}
        stage('Test') {
            steps {
                mvn test
            }            
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
