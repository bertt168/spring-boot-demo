pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'java 11'
    }
    environment {
      CC = 'clang'
    }
    stages {
        stage('Test') {
            parallel {
                stage('TEST1') {
                    steps {
                        echo 'Testing..1'
                    }
                }
                stage('TEST2') {
                    stages {
                        stage('stage1') {
//                             when {
//                                 expression {
//                                   return GIT_BRANCH == 'origin/test';
//                               }
//                                     environment name: 'CC', value: 'clang'
//                             }
                            steps {
                              echo 'pring cc'
                              echo 'pring cc'
                            }
                        }
                        stage('TEST1') {
                            steps {
                                echo 'Testing..1'
                            }
                        }
                    }
                }
            }
        }
    }
}