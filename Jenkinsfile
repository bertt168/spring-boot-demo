pipeline {
    agent any
		tools {
				// 工具名稱必須在Jenkins 管理Jenkins → 全域性工具設定中預設定。
				// maven name 跟 jdk mane 都是抓剛剛在 Global Tool Configuration 設定的name
        maven 'maven'
        jdk 'jdk11'
    }
    agent none
        stages {
            stage('1') {
                steps {
                    echo 'Hello World'
                }
            }
            stage('2') {
                steps {
                    echo "Hello World"
                }
                when {
                    beforeAgent true
                    branch 'i19'
                }
                steps {
                    echo 'Hello World'
                }
            }
        }
}