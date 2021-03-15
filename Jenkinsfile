pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path. Demo comment
      maven "maven"
      jdk "java"
                
   }

   stages {
      stage('Code Checkout') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/sidvijay18/tomcat_pipeline.git'   
         }

      }
      
      
      stage('Code Testing') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn test"
         }
      }
         
          stage('Code Build') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn package"
         }

      }
      
      stage('Code Deploy') {
         steps {
        
            // To run Maven on a Windows agent, use
           bat label: 'Deploy', script: 'copy /Y C:\Windows\System32\config\systemprofile\AppData\Local\Jenkins\.jenkins\workspace\New_freestyleproject\targetPranvat-1.0.war C:\Users\pavne\Downloads\apache-tomcat-9.0.43-windows-x86\apache-tomcat-9.0.43\webapps'
         }

      }
   }
}
