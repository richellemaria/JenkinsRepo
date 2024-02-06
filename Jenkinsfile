// pipeline {
//       agent {
//         label 'WS'
//       }
//       environment {
//            ENV_URL = "pipeline.google.com"
//            SSHCRED = credentials('SSH_CRED')
//       }
//       parameters {
//         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//         booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//         choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//      }
//     //  triggers { 
//     //     cron('H/1 * * * *')
//     //  }
//       stages {
//         stage('Parallel Stages') {
//             parallel {
//                 stage('In Parallel 1') {
//                         steps {
//                             echo "In Parallel 1"
//                             sh "sleep 1"
//                             sh "hostname"
//                         }
//                     }
//                 stage('In Parallel 2') {
//                         steps {
//                             echo "In Parallel 2"
//                             sleep 1
//                     }
//                 }
//                 stage('In Parallel 3') {
//                         steps {
//                             echo "In Parallel 3"
//                             sleep 1
//                     }
//                 }
//             }
//         }
//         stage('stage one') {
//             steps {
//                sh '''
//                echo "This is stage one"
//                echo "Name of the url is ${ENV_URL}"
//                sleep 10
//                env
//                '''
//            }
//         }
//         stage('stage two') {
//             environment {
//                 ENV_URL = "stage.google.com"
//             } 
//             input {
//                  message "Should we continue?"
//                  ok "Yes, we should."
//                  submitter "alice,bob"
//                  parameters {
//                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                  }
//             } 
//             steps {
//                echo "This is stage two"
//                echo "Name of the url is ${ENV_URL}"
//                sleep 10
//             }     
//         }
//         stage('stage three') {
//             when { anyOf{
//                 branch 'dev' 
//                 changeset "**/*.js"
//                 } 
//                 }
//             steps {
//               sh '''
//                echo "This is stage three"
//                echo "Name of the url is ${ENV_URL}"
//                echo -e "\\e[31m Hii "
//                sleep 10
//                '''
//             }
//         }
//         stage('stage four'){
//             steps {
//               sh '''
//                echo "This is stage three"
//                echo "Name of the url is ${ENV_URL}"
//                echo -e "\\e[31m Welcome "
//                sleep 10
//                '''
//             }           
//         }

//       }
//       post{
//         always { 
//             cleanWs()
//         }
//       }
// }

node {
    stage('Test') {
            print "Welcome to scripted pipeline"
    }
    stage('Deploy') {
            print "Welcome to scripted pipeline"
    }
    if(env.BRANCH_NAME=='main'){
        stage('Run only on main branch') {
                echo "I only execute on main branch"
        }else{
            echo "I execute on non-main branch" 
        }
    }
}