pipeline {
    agent none

     stages {
      stage('Git Checkout') {
      agent { label 'Node 1'}
          steps { 
          git credentialsId: 'Gitcredentials', url: 'https://github.com/PitchairamanJobs/Jenkins-Terraform-Project.git'
          }
      }
        stage ("terraform init") {
           agent { label 'Node 1'}
            steps {
                bat ("terraform init -reconfigure") 
            }
        }
        
        stage ("plan") {
        agent { label 'Node 1'}
            steps {
                bat ('terraform plan') 
            }
        }

        stage (" Action") {
        agent { label 'Node 1'}
            steps {
                echo "Terraform action is --> ${action}"
                bat ('terraform ${action} --auto-approve') 
           }
        }
    }
}
    
