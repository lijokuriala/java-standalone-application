pipeline {
    agent any

   // tools {
      //  jdk 'jdk1.8.0_202'
      //  maven 'Maven3'
   // }

    stages {
        stage('Checkout') {
            steps{
            git 'https://github.com/lijokuriala/java-standalone-application.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        //stage('Run Application') {
            // write your logic here
        //}
        stage('Test') {
            steps {
                sh 'mvn test'
            }            
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
