pipeline {
  agent any
  tools {
   maven 'M2_HOME'
  }
  environment {
  registry = 'elly14/jkpipeline-demo'
  registryCredential = 'IDDocker'
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
  stage('deploy-DReg'){
      steps {
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }  
      }
    }  
   }
 }
