pipeline {
    agent { label "agent-1" }
    environment {
        project = "expense"
    }
    options {
                // Timeout counter starts BEFORE agent is allocated
                timeout(time: 10, unit: 'MINUTES')
            }
    parameters {
            string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
             text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
            choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
            password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
            }
    stages {
        stage('Build') {
            steps {
               script{
                sh """
                    echo "hello, this is build"
                    echo "i am from build stage"
                    echo "project: $project"
            
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
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
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
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
