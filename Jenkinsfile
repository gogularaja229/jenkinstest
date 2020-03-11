pipeline{
    agent any
    
    triggers{
        cron(env.BRANCH_NAME == 'master' ? 'H/5 * * * *' : '')
    }
    
    parameters {
        choice(name: 'SERVICE_NAME', choices: ['alarmsandevents', 'dbStatistics', 'managerial', 'metertransaction', 'networkcoverage', 'outagemap', 'summarymap', 'transaction'], description: 'Select the service to be deployed')
        text(name: 'BIOGRAPHY', defaultValue: 'One', description: 'Enter some information about the person')
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
   }

    
    stages{
        stage('Pre-Build') {
		steps {
                script {
                    BUILD_USER=wrap([$class: 'BuildUser']) { return env.BUILD_USER }
                }
                
            }            
        } 
        stage('Build Project'){
            steps{
                script{
                   
                    
                    if("${env.GIT_BRANCH}" == "master")
                    {
                        sh "echo ${params.SERVICE_NAME}"
                        sh "echo ${params.BIOGRAPHY}"
                        sh "echo ${BUILD_USER}"
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
