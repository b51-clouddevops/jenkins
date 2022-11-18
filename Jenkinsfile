pipeline {
    agent any 
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credentials('AWS_ACCESS_KEY')
        SSH_CRED = credentials('SSH-CRED')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3')) }
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
                 sh "echo $ACCESS_KEY"

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