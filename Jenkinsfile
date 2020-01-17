pipeline{
    agent any
    
    triggers{
        cron(env.BRANCH_NAME == 'master' ? 'H/5 * * * *' : '')
    }
    
    stages{
        stage('Build Project'){
            steps{
                sh '''
                    echo "hi"
                '''
            }
        }
    }
}
