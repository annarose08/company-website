pipeline{
  agent any
  
  stages{
    stage('Stop old container'){
      steps{
        bat 'docker rm -f company-1website || exit 0'
      }
    }
    stage('Checkout code'){
      steps{
        echo 'Pulling code from github by using jenkins'
        checkout scm
      }
    }
    stage('Build Docker image'){
      steps{
        echo 'Building Docker image'
        bat 'docker build -t company-1website .'
      }
    }
    stage('Run Docker Container'){
          steps{
            echo 'Running Docker container'
            bat 'docker run -d -p 8070:80 company-1website'
          }
        }
      
  }
}
