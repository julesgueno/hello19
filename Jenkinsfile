pipeline {
   environment {
    registry = "julesgueno/devops-pipe-test"
    registryCredential = 'DockerID1'
   }
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
     stage('test'){
       steps {
        echo "test steps"
        sh 'mvn test'
       }
     }
     stage('Deploy'){
       steps {
        script {
         docker.build registry + ":$BUILD_NUMBER" 
         }
       }
     }
   }
}    
