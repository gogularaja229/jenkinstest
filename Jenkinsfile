pipeline{
    agent any

    parameters {
        choice(name: 'SERVICE_NAME', choices: ['alarmsandevents', 'dbStatistics', 'managerial', 'metertransaction', 'networkcoverage', 'outagemap', 'summarymap', 'transaction'], description: 'Select the service to be deployed')
        text(name: 'BIOGRAPHY', defaultValue: 'One', description: 'Enter some information about the person')
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
   }

    
    stages{
        
        stage('Build Project'){
            steps{
                script{
                   
                    
                    if("${env.GIT_BRANCH}" == "master")
                    {
			sh "echo failed"
			exit 1
                        sh "echo ${params.SERVICE_NAME}"
                        sh "echo ${params.BIOGRAPHY}"
                    }
                    else
                    {
                        sh "echo not matched"
                    }
                }
            }
        }
    }
}
