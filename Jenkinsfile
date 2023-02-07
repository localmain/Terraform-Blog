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
        
        stage ("terraform action") {
            steps {
                echo "terraform action is ${action}"
                bat ('terraform ${action}') 
           }
        }
    }
}
