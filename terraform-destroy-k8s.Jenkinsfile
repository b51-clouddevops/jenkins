pipeline {
    agent any    
    parameters {
         choice(name: 'ENV', choices: ['dev', 'prod'], description: 'Chose Environment') 
    }
    options {
        ansiColor('xterm')  // Gives colored output
    }
    stages {    
     stage('DB-n-EKS') {
        parallel {
            stage('Creating-EKS') {
            steps {
                dir('EKS') {  git branch: 'main', url: 'https://github.com/b51-clouddevops/kubernetes.git'

                        sh ''' 
                            cd eks 
                            make destroy

                        ''' 
                     }
                 }
            }
         stage('DB') {
            steps {
              dir('DB') {
                git branch: 'main', url: 'https://github.com/b51-clouddevops/terraform-databases.git'
                sh "terrafile -f env-${ENV}/Terrafile"  
                sh "terraform init -backend-config=env-${ENV}/${ENV}-backend.tfvars -reconfigure"
                sh "terraform destroy -var-file=env-${ENV}/${ENV}.tfvars -auto-approve"
                         }                    
                    }
                }
            }
        }
        stage('VPC') {
            steps {
              dir('VPC') {
                git branch: 'main', url: 'https://github.com/b51-clouddevops/terraform-vpc.git'
                sh "terrafile -f env-${ENV}/Terrafile"  
                sh "terraform init -backend-config=env-${ENV}/${ENV}-backend.tfvars"
                sh "terraform destroy -var-file=env-${ENV}/${ENV}.tfvars -auto-approve"
              }                    
            }
        }
    }
}

