pipeline {
    agent any
		//指定什麼條件的 agent 可以執行這個專案，any 表示不指定，
    //任意 agent 都可以執行，這個設定相當於 UI 上的限制專案執行節點，可以用 label 指定 agent 標籤
		//label 'test'
    stages {
        stage('hello world') {
            steps {
                echo 'hello from Pipeline'
            }
        }
				stage('test') {
            steps {
                echo 'test'
            }
        }
    }
}