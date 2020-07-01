pipeline {
    agent any
     stages {
      stage('build') {
            steps {
                echo "my build operation"
            }
        }
     stage('Deploy') { 
           steps {
             sh ''' #! /bin/bash 
             
              aws deploy create-deployment --application-name MyChatApplication --deployment-group-name CFChatApp --deployment-config-name CodeDeployDefault.AllAtOnce --github-location repository=SaundaleB1995/ChatApplication,commitId=${GIT_COMMIT}
             '''
            }
        }
      }
   }
