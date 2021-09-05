pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'java 11'
    }
    stages {
        stage('Practice') {
            parallel {
                stage('TEST1') {
                    steps {
                        echo 'Testing..1'
                    }
                }
                stage('TEST2') {
                    steps {
                        echo 'Testing..2'
                    }
                    stage('TEST3') {
                        steps {
                            echo 'Testing..3'
                        }
                    }
                }
            }
        }
    }
}