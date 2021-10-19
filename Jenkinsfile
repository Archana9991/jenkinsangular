pipeline {
  tools {
    nodejs 'Node16'
  }
    agent any
    stages {
        stage('Check version') {
            steps {
                echo 'Cleaning..'
                bat 'npm --version'
            }
          post{
            
            
                success{
                    slackSend channel: '#jenkins', 

                          message: 'cleaning successfull'
                }
                failure{
                     slackSend channel: '#jenkins', 
                      

                          message: 'cleaning failure'
                
            }
        }
        }
        stage('Install dependencies') {
            steps {
                echo 'Install deps..'
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'npm test'
            }
          post{
            
            
                success{
                    slackSend channel: '#jenkins', 

                          message: 'testing successfull'
                }
                failure{
                     slackSend channel: '#jenkins', 
                      

                          message: 'testing failure'
                
            }
        }
        }
        stage('Package') {
            steps {
                echo 'npm build'
            }
        } post{
            
            
                success{
                    slackSend channel: '#jenkins', 

                          message: 'successful packaging '
                }
                failure{
                     slackSend channel: '#jenkins', 
                      

                          message: 'failure packaging '
                
            }
       }
    }

}
}
