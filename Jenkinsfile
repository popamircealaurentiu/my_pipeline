import org.yaml.snakeyaml.Yaml

def getEmailList() {
    return 'a'
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                println "Printing to Console"
            }
        }
        stage('load config') {
            steps {
                script {
                        def configVal = readYaml file: "configfile.yml"
	                    echo "configVal: " + configVal
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    if (currentBuild.currentResult == "SUCCESS") { println "a" }
                }
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
            emailext(
                body: 'success', 
                from: 'jenkins@home.com',  
                subject: 'Jenkins build', 
                to: 'popamircealaurentiu@yahoo.com'
            )
        }
        failure {
            echo "${env.BUILD_URL} has result fail"
            emailext(
                body: 'success', 
                from: 'jenkins@home.com',  
                subject: 'Jenkins build', 
                to: 'popamircealaurentiu@yahoo.com'
            )
        }
    }
}
