//Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any
		tools {
				// 工具名稱必須在Jenkins 管理Jenkins → 全域性工具設定中預設定。
				// maven name 跟 jdk mane 都是抓剛剛在 Global Tool Configuration 設定的name
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    stages { // 運行，為由上到下。當然也有進階的應用是可以平行處理的
//         stage('Practice') {
//             steps {
//                 echo 'Building..'
//             }
//         }
        stage('Practice') {
            parallel {
                stage('State 1') {
                    steps {
                        echo 'Testing..1'
                    }
                }

              stage('State 2-1'){
              	when {
              	    expression {
                        return GIT_BRANCH == 'origin/test';
                    }
              			environment name: 'CC', value: 'clang'
              	}
              	steps {
              	  echo 'pring cc'
                }
              }

                stage('State 2-2') {
                    steps ('State 2-1'){
                        echo 'Testing..2'
                    }
//                     steps ('State 2-2'){
//                            echo 'Testing..2'
//                     }
                }
            }
        }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
    }
}
