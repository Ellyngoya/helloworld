pipeline {
  agent any
  tools {
   maven 'M2_HOME'
  }
  environment {
    registry = "elly14/jkpipe-test"
    registryCredential = 'IdDocker'
    dockerImage = ''
  }
  stages {
    stage('Build'){
      steps {
        sh 'mvn clean'
        sh 'mvn install'
        sh 'mvn package'
      }
    }  
    stage('Test'){
      steps {
        sh 'mvn test'
      }
    }  
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER" 
        }
       }
     }
     stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push() 
          }
         }
       }
     }
   }
 }
