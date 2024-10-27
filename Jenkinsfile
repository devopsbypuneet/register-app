pipeline{
  agent { label 'Jenkins-Agents'}
  tools {
    jdk  'java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        cleanWS()
      }
    }
    stage("Checkout from SCM"){
      steps{
        git branch: 'main', credentialsId: 'github_with_password', url: 'https://github.com/devopsbypuneet/register-app' 
      }
    }
    stage("Build Application"){
      steps{
        sh 'mvn clean package'
      }
    }
    stage("Test Application"){
      steps{
        sh 'mvn test'
      }
    }
  }
}











