pipeline {
    agent any
    tools {
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    stages {
        stage('check env') {
            steps {
                bat 'mvn -v'
                bat 'java -version'
            }
        }
        stage('Build') {
            steps {
                //如果是mac
                //sh 'mvn -B -DskipTests clean package'

                //如果是window
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
                //sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deliver') {
            steps {
                //sh './jenkins/scripts/deliver.sh'
                bat 'jenkins/scripts/deliver.bat'
            }
        }
    }
}