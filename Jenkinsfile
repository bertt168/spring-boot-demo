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
        stage('Build') {
            when {
            	    expression {
                      return GIT_BRANCH == 'origin/test';
                  }
            			environment name: 'CC', value: 'clang'
            	}
            	steps {
            	  echo 'pring cc'
              }
        }
        stage('Test') {
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
                }
            }

        }
    }
}