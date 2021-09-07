pipeline {
    agent any
    tools {
        maven 'Maven 3.8.2'
        jdk 'jdk-15.0.2'
    }
    stages {
        stage('check env') {
            steps {
                echo '1'
            }
        }
        stages {
            stage {
                steps {
                    echo '2-1'
                }
            }
            stage {
                steps {
                    echo '2-2'
                }
            }
        }
    }
}