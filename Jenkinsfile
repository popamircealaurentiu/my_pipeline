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
                if (currentBuild.currentResult == "SUCCESS") { println "a" }
            }
        }
        stage('Deploy') {
            steps {
                println "Printing to Console"
            }
        }
        stage('AAA') {
            steps {
                echo "${currentBuild.currentResult}"
//                 if (currentBuild.currentResult == "SUCCESS") {
//                     mail bcc: '', body: 'success', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
//                 }
//                 else {
//                     mail bcc: '', body: 'failed', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
//                 }
            }
        }
    }
    post {
        success {
            echo "${env.BUILD_URL} has result success"
            mail bcc: '', body: 'success', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
        }
        failure {
            echo "${env.BUILD_URL} has result fail"
            mail bcc: '', body: 'failed', cc: '', from: 'jenkins@home.com', replyTo: '', subject: 'Jenkins build', to: 'popamircealaurentiu@yahoo.com'
        }
    }
}
