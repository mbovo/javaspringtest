pipeline {

  agent any

  stages{
    stage ("Preliminar Steps"){
      steps {
        echo "TO_DO"
      }
    }

    stage ("Chckout app code"){
      steps {
        checkout([
          $class: 'GitSCM', 
          branches: [[name: '*/master']], 
          doGenerateSubmoduleConfigurations: false, 
          extensions: [
            [$class: 'WipeWorkspace'], 
            [$class: 'CleanBeforeCheckout']
            ], 
          submoduleCfg: [], 
          userRemoteConfigs: [
            [url: 'https://github.com/mbovo/javaspringtest.git']
          ]
        ])

      }
    }

    stage ("Maven build"){
      steps{
        sh "mvn clean package"
      }
      post { 
        success { 
            archiveArtifacts artifacts: 'target/**/*.jar', fingerprint: true
        }
    }
    }
  }
}