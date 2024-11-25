pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        nodejs('Node'){
          echo 'Building application'
          sh 'npm install'
          
        }
      }
    }
  }
  post{
    success{
      slackSend(
        message: "Build succeeded"
      )
    }
    failure{
      slackSend(
        message: "Build failed"
      )
    }
    always{
      slackSend(
        message: "Build complete"
      )
    }
  }
}
