pipeline {
    agent any 
    environment {
        ENV_URL = "pipeline.google.com"
    }
    stages {
        stage('First Stage Name') {
            steps {
                echo "One"
            }
        }
        stage('Second Stage Name') {
            steps {
                 sh "echo One"
                 sh "echo ENV_URL is ${ENV_URL}"

            }
        }
        stage('Third Stage Name') {
            environment {
                ENV_URL = "pipeline.google.com"
            }
            steps {
                 sh '''
                      echo AWS
                      echo DevOps
                      echo Bash
                    '''
                }
            }
        }
    }









// pipeline {
//     /* Declarative Pipeline */
// }



// node {
//     /* scripted pipeline */
// }