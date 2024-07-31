pipeline{
    
    agent any

parameters {
  choice choices: ['develop-build-with-parameters', 'master'], description: 'select branch name', name: 'branchName'
  booleanParam(defaultValue: true, description: 'Checkout stage', name: 'Checkout')
//   booleanParam(defaultValue: true, description: 'Unit test stage', name: 'Unit_Test')
//   booleanParam(defaultValue: true, description: 'Package stage', name: 'Package')
}

stages{
//Get the code from GitHub
    stage('CheckoutCode'){
	steps{
		when{
			expression{params.Checkout}
		}
	    git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
	}
	}
  
}// Stages Closing
  
}// Pipelien CLosing
