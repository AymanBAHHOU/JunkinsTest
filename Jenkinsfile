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
               
                bat 'mvn cobertura:cobertura'
                bat 'mvn clean site'
                step([$class: 'CoberturaPublisher', coberturaReportFile: '**/target/site/cobertura/coverage.xml'])
               
            }
        }
        stage('Deploy') {
            steps {
                 bat 'mvn install'
            }
        }
    }
}
