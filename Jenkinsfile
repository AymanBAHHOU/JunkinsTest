pipeline {
    agent any
    tools {
     maven 'Maven 3.6.0'   
     jdk 'jdk 1.8'
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
}
