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
        stage('Practice') {
            parallel {
                stage('Stage 1') {
                    steps {
                        echo 'Testing..1'
                    }
                }
                stage('Stage 2') {
                    stages {
                        stage('Stage 2-1') {
                            when {
                                expression {
                                  return GIT_BRANCH == 'origin/test';
                              }
                                    environment name: 'CC', value: 'aa'
                            }
                            steps {
                              echo 'pring cc'
                              echo 'pring cc'
                            }
                        }
                        stage('Stage 2-2') {
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