pipeline {
  agent any
  environment {
      DIRECTORY_PATH = "https://github.com/Deepak-q/Task-6.2C.git"

  }

  stages {
      stage('Build') {
          steps {
              echo "Fetching the source code from the directory path specified by ${env.DIRECTORY_PATH}"
              echo "Built the code using maven"
            echo "Updated the code"
            echo"deepak"
          }
      }
      stage('Unit and integration tests') {
          steps {
              echo "Ran unit and integration tests using Junit"
          }
         post {
            success {
                  emailext  subject: 'Success:Testing Stage', 
                            body: 'Tests ran successfully', 
                            to: "deepak4881.be22@chitkara.edu.in",
                            attachLog: true
              }
           failure{
               emailext  subject: 'Failure:Testing Stage', 
                            body: 'Failed to run tests', 
                            to: "deepak4881.be22@chitkara.edu.in",
                            attachLog: true
           }
      }
           
    }
      stage('Code Analysis') {
          steps {
              echo "check the quality of the code using SonarQube"
          }
      }
     stage('Security Scan') {
          steps {
              echo "Performed Security Scan using Synk"
          }
        post {
            success {
                  emailext  subject: 'Success:Security Scan', 
                            body: 'Security scan was successful', 
                            to: "deepak4881.be22@chitkara.edu.in",
                            attachLog: true
              }
           failure{
               emailext  subject: 'Failure:Security Scan', 
                            body: 'Failed while scanning for the security', 
                            to: "deepak4881.be22@chitkara.edu.in",
                            attachLog: true
           }
      }
      }
      stage('Deploy to Staging') {
          steps {
              echo "Deployed to Staging Server (AWS EC2)"
          }
          
    }
      stage('Integration tests on Staging') {
          steps {
              echo "Ran Integration Tests using Apache Camel tool"
              echo "Updated code"
          }
      }
    stage('Deploy to Production'){
      steps{
        echo "Application deployed to production server (AWS EC2 instance)"
        
      }
      
    }
       
    
  }
}
