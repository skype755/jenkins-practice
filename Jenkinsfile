pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               script{
                sh """
                    echo "hello, this is build"
                    echo "i am from build stage"
                """
               }
            }
        }
        stage('Test') {
            steps {
                script{
                sh """
                    echo "hello, this is test"
                """
               }
            }
        }
        stage('Deploy') {
            steps {
                script{
                sh """
                    echo "hello, this is deploy"
                """
               }
            }
        }
    }
}