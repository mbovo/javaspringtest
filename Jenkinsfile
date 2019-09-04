node {
    stage "Preliminar verification"{
      echo "TODO"
    }

    stage "Checkout app" {
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
    
    stage "Build with maven" {
      sh "mvn clean package"    
    }
}
