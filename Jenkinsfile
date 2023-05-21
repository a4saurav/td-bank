pipeline {
        agent any
        tools {
        maven 'maven3'
        stages{
        stage ('build') {
        steps {
        sh script: 'mvn clean package'
        }
        }
        stage ('upload war to nexus3') {
        steps {
        sh script 'mvn clean package'
        }
        }
}
}

