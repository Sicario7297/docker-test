"""pipeline {
    environment {
        registry = "51c4r10/testing"
        registryCredential = 'dockerhub_id'
        dockerImage = 'ubuntu'
        }
    
    agent { 
        node {
            label 'kubeagent'
        }
    }
       
    stages {
        stage ('Cloning our Git') {
            steps { git branch: 'main',
                        credentialsId: 'github-pass',
                        url: 'https://github.com/Sicario7297/docker-test.git'
            }
        }
        stage ('Building our image') { 
            steps { 
                script { 
                    dockerImage = docker.build registry + ":1" 
                }
            } 
        }
    }
}
"""

pipeline {
    agent { docker { image 'maven:latest' } }
    stages {
        stage('log version info') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
    }
}
