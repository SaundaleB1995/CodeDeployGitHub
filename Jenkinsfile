pipeline {
    agent any
         stages {
         stage('Sonarqube') {
           environment {
                scannerHome = tool 'sonar-scanner'
                }
         steps {
            withSonarQubeEnv('sonar-scanner') {
                sh "${scannerHome}/bin/sonar-scanner"
            }
            timeout(time: 5, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
            }
          }
         }
        stage('Build') { 
           steps {
             echo "Bhushan"
            }
        }
         
     stage('Deploy') { 
           steps {
             sh ''' #! /bin/bash 
            
              aws deploy create-deployment --application-name ChatApp --deployment-group-name CFChatApp --deployment-config-name CodeDeployDefault.AllAtOnce --github-location repository=SaundaleB1995/ChatApplication,commitId=${GIT_COMMIT}
             '''
            }
        } 
              stage('status'){
            steps {
            sh ''' #! /bin/bash
            echo Deployment started
            '''
            }  
        }  
    }
    post { 
        always { 
            echo 'chat application stage is success'
        }
    }   
}
