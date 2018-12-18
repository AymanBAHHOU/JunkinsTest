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
        stage('couverture') {
            steps {
               
                bat 'mvn cobertura:cobertura'
                 bat 'mvn clean site'
            }
              post {
        always {
           
            cobertura coberturaReportFile: '**/target/site/cobertura/coverage.xml', failNoReports: true
}
               
            }
        }
        
    }

