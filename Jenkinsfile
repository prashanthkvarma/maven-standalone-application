pipeline {
    agent any

parameters {
  choice choices: ['master', 'develop-branch-stage-separation'], description: 'select branch name', name: 'branchName'
//  string(name: 'BRANCH_NAME', defaultValue: '', description: 'Branch to build')
}

    stages {
        stage('Build') {
            when {
                anyOf {
                    branch 'develop-branch-stage-separation'
                    branch 'master'
                }
            }
            steps {
                sh "echo Running build for branch: ${env.BRANCH_NAME}"
                git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
            }
        } // build stage close
        
        stage('Test') {
            when {
                anyOf {
                    branch 'develop-branch-stage-separation'
                    branch 'master'
                }
            }
            steps {
                sh "echo Running build for branch: ${env.BRANCH_NAME} "
                sh "mvn test"
            }
        } // Test stage close

        stage('Package') {
            when {
                anyOf {
                    branch 'master'
                }
            }
            steps {
                sh "echo Running build for branch: ${env.BRANCH_NAME}"
                sh "mvn package"
            }
        } // Package stage close
    }
}
