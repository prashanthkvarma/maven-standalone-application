pipeline {
    agent any

parameters {
  choice choices: ['develop', 'hotfix/*'], description: 'select branch name', name: 'branchName'
}

    stages {
//      def branchName = env.BRANCH_NAME
       
        stage('Checkout') {
            when {
                anyOf{
                    branch 'develop'
                    
                    branch 'hotfix/*'
                }
            }
            steps {
                git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
            }
        }


        stage('Unit Test') {
            when {
                anyOf{
                    branch 'develop'
                    
                    branch 'hotfix/*'
                }
            }
            steps {
                sh "mvn test"
            }
        }
        
      
        stage('Package') {
            when {
                branch 'develop'
            }
            steps {
                sh "mvn clean package"
            }
        } 
    } // stages closing
} // pipeline closing