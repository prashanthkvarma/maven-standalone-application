pipeline{
    
    agent any

parameters {
  choice choices: ['develop-dynamic-branch-trigger', 'master'], description: 'select branch name', name: 'branchName'
}

stages{
//Get the code from GitHub
    stage('CheckoutCode'){
        steps{
            script{
                def branchName = params.BRANCH_NAME
                if (branchName == 'master') {
                    git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
                    sh "echo 'The branch name is env.BRANCH_NAME' "
                } 
                // else {
                //     error "Unsupported branch: ${branchName}"
                // }
            }
            
        }
	}
  
}// Stages Closing
  
}// Pipelien CLosing