pipeline {
    agent any
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages {
        stage ('get code') {
            steps {
                git 'https://github.com/a4saurav/td-bank.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn clean package'
            
            }
        }
        stage ('sonarqube analysis') {
            steps {
                withSonarQubeEnv ('sonarqube-server')
                sh 'mvn sonar:sonar'
            }
            }
        }
        }
    }
