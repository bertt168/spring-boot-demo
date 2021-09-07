//Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any
		tools {
				// 工具名稱必須在Jenkins 管理Jenkins → 全域性工具設定中預設定。
				// maven name 跟 jdk mane 都是抓剛剛在 Global Tool Configuration 設定的name
        maven 'maven 3.8.2'
        jdk 'jdk-15.0.2'
    }
    stages { // 運行，為由上到下。當然也有進階的應用是可以平行處理的
        stage('Build') {
            steps {
                echo 'Building..'
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
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}