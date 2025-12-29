pipeline {
  agent any
  environment {
     PATH = "/opt/maven/bin:$PATH"
  }

  stages {

     stage ('clone') {
      steps {
       git url: 'https://github.com/AmithDevOps7907/saidemytrend.git', branch: 'main'
      }
    }

     stage ('sonarQube analysis') {
      environment {
        scannerHome = tool 'mithu-sonarqube-scanner'
      }

      steps {
        withSonarQubeEnv('mithu-sonarqube-server') {
        sh "${scannerHome}/bin/sonar-scanner"

        }
      }
    }
  }
}
       
