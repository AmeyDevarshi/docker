pipeline {
    agent any
//     agent {
//         docker {
//             image 'maven:3-alpine'
//             args '-v /root/.m2:/root/.m2'
//         }
//     }
    stages {
        stage('Build') {
            steps {
                batchFile 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                batchFile 'docker build docker1'
            }
//             post {
//                 always {
//                     //junit 'target/surefire-reports/*.xml'
//                     clean ws
                }
            }
        }
    }
}
