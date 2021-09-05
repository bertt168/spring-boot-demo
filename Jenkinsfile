pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'java 11'
    }
    stages {
        stage('Build') {
            when {
        	    expression {
                  return GIT_BRANCH == 'origin/test';
              }
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