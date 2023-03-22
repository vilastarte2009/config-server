pipeline {
    agent any
    tools{
        maven 'maven3'
    }
    stages{
       stage('Build Config Server'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/config-server.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker Build Config Server'){
           steps{
               bat 'docker build -t vilastarte/config-server:latest .'
           }
       }
       
       stage('Docker push config server'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/config-server:latest'
               }
                   
               }
           }
       
       //////Naming Server
       stage('Build Naming Server'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/naming-server.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker Build Naming Server'){
           steps{
               bat 'docker build -t vilastarte/naming-server:latest .'
           }
       }
       
       stage('Docker push naming server'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/naming-server:latest'
               }
                   
               }
           }
           
        ////// API Gateway
        stage('Build API Gateway'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/api-gateway.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker build api-gateway'){
           steps{
               bat 'docker build -t vilastarte/api-gateway:latest .'
           }
       }
       
       stage('Docker Push API Gateway'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/api-gateway:latest'
               }
                   
               }
           }
       
        ////// SAL - Service
        stage('Build Sal -Service'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/sal-service.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker Build Sal Service'){
           steps{
               bat 'docker build -t vilastarte/sal-service:latest .'
           }
       }
       
       stage('Docker Push Sal Service'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/sal-service:latest'
               }
                   
               }
           }
     
        ////// Day - Service
        stage('Build Day-Service'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/day-service.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker build day-service'){
           steps{
               bat 'docker build -t vilastarte/day-service:latest .'
           }
       }
       
       stage('Docker Push Day Service'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/day-service:latest'
               }
                   
               }
           }
       
       ////// Adv - Service
        stage('Build advance-service'){
           steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vilastarte2009/advance-service.git']])
               bat 'mvn clean install'
           }
       }
       stage('Docker build advance-service'){
           steps{
               bat 'docker build -t vilastarte/day-service:latest .'
           }
       }
       
       stage('Push Docker image advance-servicer'){
           steps{
               script{
                   withCredentials([string(credentialsId: 'docker_hub_pwd', variable: 'docker_hub_pwd')]) {
                   bat 'docker login -u vilastarte -p Sonali@11'
                     }
                   bat 'docker push vilastarte/advance-service:latest'
               }
                   
               }
           }
       
        
    }
    }
