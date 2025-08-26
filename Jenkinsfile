pipeline {
    agent { label "agent-1" }
    environment {
        project = "expense"
    }
    options {
                // Timeout counter starts BEFORE agent is allocated
                timeout(time: 5, unit: 'SECONDS')
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