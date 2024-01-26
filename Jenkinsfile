pipeline {
      agent any
      environment {
           ENV_URL = "pipeline.google.com"
           SSH_CRED = credentials('SSH_CRED')
      }
      stages {
        stage('stage one') {
            steps {
               echo "This is stage one"
               echo "Name of the url is ${ENV_URL}"
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
               echo "This is stage three"
               echo "Name of the url is ${ENV_URL}"
            }
        }

      }
}