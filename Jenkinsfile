pipeline{
    agent any
    
    triggers{
        cron(env.BRANCH_NAME == 'master' ? 'H/5 * * * *' : '')
    }
    
    parameters {
        choice(name: 'SERVICE_NAME', choices: ['alarmsandevents', 'dbStatistics', 'managerial', 'metertransaction', 'networkcoverage', 'outagemap', 'summarymap', 'transaction'], description: 'Select the service to be deployed')
   }

    
    stages{
        stage('Build Project'){
            steps{
                script{
                    if("${env.GIT_BRANCH}" == "master" && "${params.SERVICE_NAME}" == "dbStatistics")
                    {
                        sh "echo ${params.SERVICE_NAME}"
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
