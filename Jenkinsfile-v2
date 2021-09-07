pipeline {
    agent any
    tools {
        maven 'Maven 3.8.2'
        jdk 'jdk-15.0.2'
    }
    stages {
        stage('check env') {
            steps {
                sh 'mvn -v'
                sh 'java -version'
            }
        }
        stage('Build') {
            steps {
                echo 'clean package' //先清除再打包
                echo '-DskipTests' //跳過測試
                echo '-b' //該引數表示讓Maven使用批處理模式構建專案
                //如果是mac
                //sh 'mvn -B -DskipTests clean package'

                //如果是window
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
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
                sh 'jenkins/scripts/deliver.sh'
            }
        }
    }
}