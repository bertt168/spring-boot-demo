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
        stage('test parallel') {
            parallel {
                stage('Stage 1') {
                    steps {
                        echo "In Stage 1"
                    }
                }
                stage('Stage 2') {
                    stages {
                        stage('Stage 2-1') {
                            when {
                                environment name: 'XX_PATH', value: 'D://jenkins/'
                            }
                            steps {
                                echo "In Stage 2-1"
                            }
                        }
                        stage('Stage 2-2') {
                            steps {
                                echo "In Stage 2-2"
                            }
                        }
                    }
                }
            }
        }
    }
}