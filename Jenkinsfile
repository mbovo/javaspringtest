node {
    stage "Create build output"
    
    sh "mvn clean package"

    stage "Archive build output"
    
    // Archive the build output artifacts.
    archiveArtifacts artifacts: 'target/*.jar', excludes: 'target/*'
}
