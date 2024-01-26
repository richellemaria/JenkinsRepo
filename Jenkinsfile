pipeline {
      agent any
      environment {
           ENV_URL = "pipeline.google.com"
           SSHCRED = credentials('SSH_CRED')
      }
      parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
     }
    //  triggers { 
    //     cron('H/1 * * * *')
    //  }
      stages {
        stage('stage one') {
            steps {
               sh '''
               echo "This is stage one"
               echo "Name of the url is ${ENV_URL}"
               sleep 10
               env
               '''
           }
        }
        stage('stage two') {
            environment {
                ENV_URL = "stage.google.com"
            } 
            input {
                 message "Should we continue?"
                 ok "Yes, we should."
                 submitter "alice,bob"
                 parameters {
                   string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                 }
            } 
            steps {
               echo "This is stage two"
               echo "Name of the url is ${ENV_URL}"
               sleep 10
            }     
        }
        stage('stage three') {
            when { 
                branch 'dev' 
                changeset "**/*.js"
                }
            steps {
              sh '''
               echo "This is stage three"
               echo "Name of the url is ${ENV_URL}"
               echo -e "\\e[31m Hii "
               sleep 10
               '''
            }
        }
        stage('stage four'){
            steps {
              sh '''
               echo "This is stage three"
               echo "Name of the url is ${ENV_URL}"
               echo -e "\\e[31m Welcome "
               sleep 10
               '''
            }           
        }

      }
}