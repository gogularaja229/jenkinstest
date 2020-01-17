pipeline{
    agent any
    
    triggers{
        cron(env.BRANCH_NAME == 'master' ? '00 22 * * *' : '')
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
