pipeline {
    agent any
    tools {
     maven 'apache-maven-3.5.4'   
     jdk 'jdk1.8.0_161'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn compiler:compile'
               
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
               
            }
        }
        stage('Deploy') {
            steps {
                 bat 'mvn install'
            }
        }
    }
}
