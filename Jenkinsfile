pipeline {
    agent any
    tools {
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    environment {
        XX_PATH = '../'
    }
    stages {
        stage('hello world') {
            when {
                environment name: 'XX_PATH', value: 'D://jenkins/'
            }
            steps {
                echo 'hello from Pipeline'
            }
        }
        stage('env') {
            steps {
                bat 'set'
            }
        }
    }
}