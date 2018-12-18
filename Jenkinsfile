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
            }
               post{
 success{
 step([$class: 'CoberturaPublisher', 
 autoUpdateHealth: false, 
 autoUpdateStability: false, 
 coberturaReportFile: '**/target/site/cobertura/coverage.xml',
 failUnhealthy: false,
 failUnstable: false, 
 maxNumberOfBuilds: 0, 
 onlyStable: false,
 sourceEncoding: 'ASCII', 
 zoomCoverageChart: false])
}
}
               
            }
        }
        
    }

