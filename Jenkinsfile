pipeline {
    agent any

    stages {
        stage('w/o Docker') {
            steps {
                sh '''
                echo "Without Docker"
                ls -la
                touch container-no.txt
                '''
            }
        }

        stage('w/ Docker') {
            agent {
                docker {
                   image 'node:18-alpine'
                   reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                echo "With Docker"
                touch container-yes.txt
                '''
            }
        }
    }
}
