pipeline {
    agent any
    tools {
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    stages {
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
            }
//             看起來需額外安裝junit plugin 先略過
//             post {
//                 always {
//                     junit 'target/surefire-reports/*.xml'
//                 }
//             }
        }
    }
}