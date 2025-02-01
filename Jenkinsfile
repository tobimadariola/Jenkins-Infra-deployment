pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="654654598041"
        AWS_DEFAULT_REGION="us-east-1"     
    }
        
    stages {
        stage('provision sonarqube-server') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('aws_access_key_id')
             AWS_SECRET_ACCESS_KEY = credentials('aws_secret_access_key')
           }
           steps {
              script {
                  sh "terraform init"
                  sh "terraform validate"
                  sh "terraform plan"
                  sh " terraform destroy --auto-approve"
            }
        }
               
     }
    }
    
}
