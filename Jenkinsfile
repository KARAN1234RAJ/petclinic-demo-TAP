pipeline{
   environment {
    registry = "kr1412/petclinic"
    registryCredential = 'docker_hub_kr1412'
    dockerImage = ''
  }
  
  agent any
  stages{
    stage('Build'){
    steps{
      echo "Building Project"
      sh './mvnw package'
    }
  }
   stage('Archive'){
    steps{
      echo "Archiveing Project"
      archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
    }
  }
     stage('Build Docker Image'){
    steps{
      echo "Building Docker"
       script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
    }
  }
     stage('Push Docker Image'){
    steps{
      echo "Pushing Docker Image"
        script {
        withDockerRegistry(credentialsId: 'docker_hub_kr1412') {
              dockerImage.push()
              dockerImage.push('latest')
          }
        }
    }
  }
     stage('Deploy to Dev'){
    steps{
      echo "Deploying to Dev Environment"
    }
  }
 } 
}
