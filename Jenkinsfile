pipeline{
    
    agent any

parameters {
  choice choices: ['develop-build-with-parameters', 'master'], description: 'select branch name', name: 'branchName'
}

stages{
//Get the code from GitHub
    stage('CheckoutCode'){
	steps{
	    git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
	}
	}
  
}// Stages Closing
  
}// Pipelien CLosing
