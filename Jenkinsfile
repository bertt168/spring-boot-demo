pipeline {
    agent any
		//指定什麼條件的 agent 可以執行這個專案，any 表示不指定，
        //讓 Jenkins 為你的建置工作找到一個 label 為 ec2 的 node ，
		//連線到該 ec2 node 的 ssh agent ，然後直接在上面運行你的建置 (Build)
		// agent {
		//     node {
		//         label 'ec2'
		//     }
		// }
    stages { //是一個集合，裡面可以包含很多個stage
        stage('hello world') {
            steps {
                echo 'hello from hello3'
            }
        }
    }
}