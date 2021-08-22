pipeline {
    agent any
		tools {
				// maven name 跟 jdk mane 都是抓剛剛在 Global Tool Configuration 設定的name
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}