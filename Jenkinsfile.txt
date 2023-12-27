pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from GitHub
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/red0074/jenkinpipelinejava.git']]])
            }
        }

        stage('Run') {
            steps {
                // Run your Java application
                sh 'javac Nothing.java' // Replace with your actual Java file name
                sh 'java Nothing'
            }
        }
    }
}
