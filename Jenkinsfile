pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/localmain/Terraform-Blog.git']]])            

          }
        }
        
        stage ("terraform init") {
            steps {
                bat ('terraform init') 
            }
        }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}
                bat ('terraform ${action} --auto-approve') 
           }
        }
    }
}
