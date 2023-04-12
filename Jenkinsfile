pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                println "Printing to Console"
            }
        }
        stage('Test') {
            steps {
                println "Printing to Console"
            }
        }
        stage('Deploy') {
            steps {
                println "Printing to Console"
            }
        }
        post{
            always{
                emailext to: "popamircealaurentiu@yahoo.com",
                subject: "Test Email",
                body: "Test"
            }
        }
    }
}
