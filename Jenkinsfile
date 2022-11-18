pipeline {
    agent any 
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credentials('')
    }
    stages {
        stage('First Stage Name') {
            steps {
                sh "echo One"
                sh "env"
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
                ENV_URL = "stage.google.com"
            }
            steps {
                 sh "echo ENV_URL is ${ENV_URL}"
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