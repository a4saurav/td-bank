pipeline {
    agent any
    tools {
        maven 'maven3'
    }
        stages {
            stage ('Build') {
                steps {
                    sh script: 'mvn clean package'
                }
            }
            stage ('upload war file to nexus') {
                steps {
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'td-bank',
                        classifier: '',
                        file: 'target/td-bank-0.0.1-SNAPSHOT.jar', 
                        type: 'jar']
                    ],
                    credentialsId: 'nexus3', groupId: 'com.tcs', 
                    nexusUrl: '20.55.6.188:8081', nexusVersion: 'nexus3', 
                    protocol: 'http', repository: 'maven-project', 
                    version: '0.0.1-SNAPSHOT'
            }
        }
    }
}
