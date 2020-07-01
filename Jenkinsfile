pipeline {
    agent any
     stages {
     stage('Deploy') { 
           steps {
             sh ''' #! /bin/bash 
             
              aws deploy create-deployment --application-name MyChatApplication --deployment-group-name CFChatApp --deployment-config-name CodeDeployDefault.AllAtOnce --github-location repository=https://github.com/SaundaleB1995/ChatApplication,commitId=${GIT_COMMIT}
             '''
            }
        }
      }
   }
