pipeline { 
    agent any  
       
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh "cd .."
                    sh "cd testing-deploy"
                    sh "scp -p ssh root@13.233.158.29:/var/www/html/stroberi2"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                    
                 }
            }
        }
    }
}
