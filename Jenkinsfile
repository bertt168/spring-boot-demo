pipeline {
    agent {
        // Equivalent to "docker build -f Dockerfile.build --build-arg version=1.0.2 ./build/
        dockerfile {
            filename 'Dockerfile.build'
            dir 'build'
            label 'spring-boot-demo'
            additionalBuildArgs  '--build-arg version=1.0.2'
            args '-v /tmp:/tmp'
        }
    }
    stages {
        stage('check env') {
            steps {
                bat 'mvn -v'
                bat 'java -version'
            }
        }
        stage('Build') {
            steps {
                echo 'clean package 先清除再打包'
                echo '-DskipTests 跳過測試'
                echo '-b 該引數表示讓Maven使用批處理模式構建專案'
                //如果是mac
                //sh 'mvn -B -DskipTests clean package'

                //如果是window
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
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
                bat 'jenkins/scripts/deliver.bat'
            }
        }
    }
}