pipeline {
    agent any
		tools {
				// 工具名稱必須在Jenkins 管理Jenkins → 全域性工具設定中預設定。
				// maven name 跟 jdk mane 都是抓剛剛在 Global Tool Configuration 設定的name
        maven 'maven'
        jdk 'jdk11'
    }
    stages { //是一個集合，裡面可以包含很多個stage
        stage('practice') {
            steps {
                echo 'hello from Pipeline'
            }
            stage{
                echo 'test'
            }
        }
    }
}