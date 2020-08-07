pipeline{
  
  Agent any
  stages{
    stage('Build'){
    steps{
      echo "Building Project"
    }
  }
   stage('Archive'){
    steps{
      echo "Archiveing Project"
    }
  }
     stage('Build Docker Image'){
    steps{
      echo "Building Docker"
    }
  }
     stage('Push Docker Image'){
    steps{
      echo "Pushing Docker Image"
    }
  }
     stage('Deploy to Dev'){
    steps{
      echo "Deploying to Dev Environment"
    }
  }
 } 
}
