

pipeline {
    agent any
    environment {
        PROJECT = "rest-assured"
    }

    stages {
        stage('check env') {
            steps {
                sh "java -version"
            }
        }

        stage('Clear file') {
            steps {
            	sh "chmod +x mvnw"
                sh "./mvnw clean"
            }
        }

        stage('Test') {
          steps {
            sh "./mvnw compile"
            sh "./mvnw test  -DsuiteXmlFile=./test-suite/DemoTestSuite.xml"
          }
        }

        stage('Report ') {
          steps {
            archiveArtifacts artifacts: './reports/*.html', fingerprint: true
          }
        }
    }
}
