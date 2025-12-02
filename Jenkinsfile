pipeline {
    agent {
        node{
            label 'slave-node'
        }
    }
    
    environment {
        PATH = "/opt/apache-maven-3.9.11/bin:$PATH"
    }
    stages {
        stage('CLone code from GIThub for Tweet trend') {
            steps {
                git branch: 'main', url: 'https://github.com/Deepakcodec/tweet-trend.git'
            }
        }
        
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
        }
    }
}