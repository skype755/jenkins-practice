pipeline {
    agent { label "agent-1" }
    environment {
        project = "expense"
    }
    stages {
        stage('Build') {
            steps {
               script{
                sh """
                    echo "hello, this is build"
                    echo "i am from build stage"
                    echo "project: $project"
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