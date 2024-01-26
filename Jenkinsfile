pipeline {
      agent any
      environment {
           ENV_URL = "pipeline.google.com"
           SSHCRED = credentials('SSH_CRED')
      }
      stages {
        stage('stage one') {
            steps {
               sh '''
               echo "This is stage one"
               echo "Name of the url is ${ENV_URL}"
               env
               '''
           }
        }
        stage('stage two') {
            environment {
                ENV_URL = "stage.google.com"
            }  
            steps {
               echo "This is stage two"
               echo "Name of the url is ${ENV_URL}"
            }     
        }
        stage('stage three') {
            steps {
              sh '''
               echo "This is stage three"
               echo "Name of the url is ${ENV_URL}"
               echo -e "\\e[31m Hii "
               '''
            }
        }

      }
}