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
     stage('test'){
       steps {
        echo "test steps"
        sh 'mvn test'
       }
     }
      
     stage('Deploy'){
       steps {
        echo "Deploys steps"
        sleep 10
       }
     }
     stage('Docker'){
       steps {
        echo "Images steps"
        sleep 10
       }
     } 
   }
}    
