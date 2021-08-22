pipeline {
    agent any
    tools {
        maven 'maven 3.8.2'
        jdk 'JDK 1.8'
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
//             看起來需額外安裝junit plugin 先略過
//             post {
//                 always {
//                     junit 'target/surefire-reports/*.xml'
//                 }
//             }
        }
        stage('Artifact') {
            step([$class: 'ArtifactArchiver', artifacts: '**/target/*.jar', fingerprint: true])

            try{
                stage 'Approve, go production'
                def url = 'http://localhost:8081/'
                input message: "Does staging at $url look good? ", ok: "Deploy to production"
            }finally{
                bat "ssh jenkins@localhost 'kill `cat deploy/release/run.pid`'"
            }
        }

        stage('deploy') {
            steps {
                bat 'make deploy-default'
            }
        }
    }
}