pipeline {
   agent any
   enviornment {
      PATH = "/opt/maven/bin:$PATH"
   }

   stages {
    
      stage ('clone') {
        steps {
           git url: 'https://github.com/AmithDevOps7907/saidemytrend.git', branch: 'main'
    
      stage ('SonarQube Analysis') {
      environment {
        scannerHome = tool 'ami-sonar'
      }
         steps {
            withSonarQubeEnv('Sonar-server') {
            sh "${scannerHome}/bin/sonar-scanner"
            }
          }
        }
      }
     }
    }
   }
