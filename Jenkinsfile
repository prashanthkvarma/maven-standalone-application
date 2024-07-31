pipeline{
    
    agent any

parameters {
  choice choices: ['develop-boolen-parameter', 'develop-build-with-parameters', 'master'], description: 'select branch name', name: 'branchName'
  booleanParam(defaultValue: true, description: 'Checkout stage', name: 'Checkout')
  booleanParam(defaultValue: true, description: 'Unit test stage', name: 'Unit_Test')
  booleanParam(defaultValue: true, description: 'Package stage', name: 'Package')
}

stages{
//Get the code from GitHub
    stage('CheckoutCode'){
		when{
			expression {params.Checkout}
		}
	    steps{
	      git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
	}
	}

	stage ('unit test'){
		when{
            expression{params.Unit_Test}
        } 
        steps{
            sh "mvn test"
        } //Steps close
    } // unit test stage close

	stage ('unit package'){
		when{
            expression{params.Package}
        } 
        steps{
            sh "mvn clean package"
        } //Steps close
    } // unit test stage close
  
}// Stages Closing
  
}// Pipelien CLosing
