pipeline {
    agent any
     stages {
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
            echo 'Stage is success'
        }
    }
  }
