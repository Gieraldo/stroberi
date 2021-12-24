pipeline { 
    agent any  
       
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh "pwd"
                    sh "scp -p * ssh root@13.233.158.29:/var/www/html/stroberi"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                    
                 }
            }
        }
    }
}
