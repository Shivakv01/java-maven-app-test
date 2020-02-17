pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
        jdk 'jdk13'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M3_HOME = ${M3_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -v' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
