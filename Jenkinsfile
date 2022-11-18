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
                 echo "One"
                 
            }
        }
        stage('Third Stage Name') {
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