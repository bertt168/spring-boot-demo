pipeline {
    agent any
    tools {
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
    }
    stage('Hello') {
        steps {
            script{
                def s = "Hello World"
                println s
            }
            echo 'Hello World'
        }
    }
}