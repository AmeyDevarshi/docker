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
                batchFile 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                batchFile 'docker build -t docker1'
            }
            post {
                always {
                    //junit 'target/surefire-reports/*.xml'
                    clean ws
                }
            }
        }
    }
}
