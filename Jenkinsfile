pipeline {
    agent any
     tools { 
        maven 'maven'
    }
    stages 
    {
        stage ('checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/developer']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/18hk18/java-docker.git']]])
            }
        }
       
        stage ('Build') {
            steps {
                script {
                sh 'mvn -Dmaven.test.failure.ignore=true install'
                }
            }
        }
  }  
}
