pipeline{
    
    agent any

parameters {
  choice choices: ['master', 'develop-stage-separation'], description: 'select branch name', name: 'branchName'
//  string(name: 'BRANCH_NAME', defaultValue: '', description: 'Branch to build')
}

stages{
//Get the code from GitHub
    def BRANCH_NAME = params.branchName
    if (BRANCH_NAME == 'develop-stage-separation') {
        stage('CheckoutCode'){
            steps{
            //    script{
                    // def BRANCH_NAME = params.branchName
                    // if (BRANCH_NAME == 'develop-dynamic-branch-trigger') {
                    git branch: "${params.branchName}", credentialsId: 'github_creds', url: 'https://github.com/prashanthkvarma/maven-standalone-application.git'
                    sh "echo 'The branch name is ${env.BRANCH_NAME}' "
                } // steps closed

    // stage ('unit test'){
    //     steps{
    //     //     when{
    //     //     expression{params.Unit_Test}
    //     // } 
    //         sh "mvn test"
    //     } //Steps close
    // } // unit test stage close
    // }

    }// Stages Closing
  
} // Pipelien CLosing
    //             if (BRANCH_NAME == 'master') {
    //                 sh "echo 'The branch name is ${env.BRANCH_NAME}' "
    //             }                 
    //             // else {
    //             //     error "Unsupported branch: ${branchName}"
    //             // }
    //         }
            
    //     }
	// }
}
}