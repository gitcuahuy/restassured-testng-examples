

pipeline {
    agent any
    environment {

    }

    stages {
        stage('check env') {
            steps {
                sh "java -version"
            }
        }

        stage('Clear file') {
            steps {
                sh " ./mvnw clean"
            }
        }

        stage('Test') {
          steps {
            sh "./mvnw test  -DsuiteXmlFile=./test-suite/DemoTestSuite.xml"
          }
        }

        stage('Report ') {
          steps {
            archiveArtifacts artifacts: '**/reports/*.html', fingerprint: true
          }
        }
    }
}
