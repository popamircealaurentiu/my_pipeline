import org.yaml.snakeyaml.Yaml

def getEmailList() {
    return 'a'
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    //println "Printing to Console"
                    def ret = sh(script: 'pwd', returnStdout: true)
                    println ret
                    def ret1 = sh(script: 'whoami', returnStdout: true)
                    println ret1
                }
            }
        }
        stage('load config') {
            steps {
                script {
                    def ret = sh(script: 'ls -la', returnStdout: true)
                    println ret

                    InputStream inputStream = new FileInputStream("test.yaml");

                    Yaml yaml = new Yaml();
                    Map<String, Object> data = yaml.load(inputStream);
                    System.out.println(data);
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
//             emailext(
//                 body: 'success',
//                 from: 'jenkins@home.com',
//                 subject: 'Jenkins build',
//                 to: 'popamircealaurentiu@yahoo.com'
//             )
        }
        failure {
            echo "${env.BUILD_URL} has result fail"
//             emailext(
//                 body: 'success',
//                 from: 'jenkins@home.com',
//                 subject: 'Jenkins build',
//                 to: 'popamircealaurentiu@yahoo.com'
//             )
        }
    }
}
