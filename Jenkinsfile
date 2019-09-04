node {
    stage "Create build output"

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
    
    sh "mvn clean package"    
}
