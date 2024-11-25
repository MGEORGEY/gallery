pipeline{
  agent any
  environment {
    Web_Addr = 'https://gallery-tbw1.onrender.com/'
 }
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
        message: "Build succeeded."
      )
    }
    failure{
      slackSend(
        message: "Build failed."
      )
    }
    always{
      slackSend(
        message: "Build complete. Build Id: ${env.BUILD_ID}. Website is located at: ${env.Web_Addr}"
      )
    }
  }
}
