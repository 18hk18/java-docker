pipeline {
    agent any
    stages 
    {
        stage ('checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/developer']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/18hk18/java-docker.git']]])
            }
        }
       
        stage ('Build docker image') {
            steps {
                script {
                dockerImage = docker.build registry + ":$BUILD_NUMBER"
                //dockerImage = docker.build registry + ":$BUILD_NUMBER"

                }
            }
        }
  }  
}
