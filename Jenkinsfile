pipeline {
    agent any
    tools {
     maven 'Maven 3.6.0'   
     jdk 'jdk 1.8'
    }
    stages {
    stage('Build'){
      steps {
        bat 'mvn clean install'
      }
        post{
            success{
                junit 'target/surefire-reports/**/*.xml'
            }
        }  
    }
    
    stage('Test'){
      steps {
        echo 'Testing ..'
      }
    }
    
    stage('Deploy'){
      steps {
        echo 'Deploying ..'
      }
    }
    
  }  
}
