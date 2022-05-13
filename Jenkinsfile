pipeline {
    environment {
        registry = "https://hub.docker.com/repository/docker/51c4r10/testing"
        registryCredential = 'dockerhub_id'
        dockerImage = 'ubuntu:latest'
        }
    agent { 
        node {
            label 'kubeagent'
        }
    } 
    stages {
        stage ('Cloning our Git') {
            steps { 'git@github.com:Sicario7297/docker-test.git'
            }
        }
    }       
