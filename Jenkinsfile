pipeline {
    agent any
    tools {
        maven 'maven-tool'
    }
    stages {
        stage( 'verify') {
            steps{
                sh 'mvn -v'
            }
        }
        stage( compile) {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage( test) {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
