pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Potharlanka-Goutham/java-pipeline.git'
            }
        }

        stage('Build and Run Java') {
            steps {
                script {
                    def javaHome = tool 'JDK' // Assuming JDK is configured in Jenkins tools
                    def classpath = "${javaHome}/bin"
                    sh "javac -cp ${classpath} Pipeline.java"
                    sh "java -cp ${classpath} Pipeline"
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed. Please check the logs for details.'
        }
    }
}
