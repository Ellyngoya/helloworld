pipeline {
  agent any
  tools {
   maven 'M2_HOME'
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
  stage('deploy'){
      steps {
        echo "Deploy step"
        sleep 10
      }
    }  
  stage('docker'){
      steps {
        echo "docker step"
        sleep 10
      }
    }  
   }
 }
