pipeline {
    agent any
    stages {
        stage('Puck Blog 範例') {
            parallel {
                stage('Stage 1') {
                    steps {
                        echo "In Stage 1"
                        sleep(10)
                    }
                }
                stage('Stage 2') {
                    stages {
                        stage('Stage 2-1') {
                            steps {
                                echo "In Stage 2-1"
                                sleep(5)
                            }
                        }
                        stage('Stage 2-2') {
                            steps {
                                echo "In Stage 2-2"
                                sleep(5)
                            }
                        }
                    }
                }
            }
        }
    }
}