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
        stage('AAA'){
            steps {
                if (currentBuild.currentResult == "SUCCESS") {
                    mail bcc: '', body: 'success', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
                }
                else {
                    mail bcc: '', body: 'failed', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
                }
            }
        }
    }
}
