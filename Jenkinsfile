pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
        
        //Stage 3:publish artifacts to Nexus
        stage ('publish to nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: 'admin', groupId: 'com.vinaysdevopslab', nexusUrl: '172.16.10.83:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'SathishDevopsLab-SNAPSHOT', version: '0.0.4-SNAPSHOT'
            }
            
        }
        // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo 'deploying.....'

                
             }
            }
        }
           
  }
