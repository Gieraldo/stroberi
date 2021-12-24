pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh "ssh root@3.111.35.31"
                    sh "cd /var/www/html/stroberi"
                    sh "git pull origin master"
                 }
            }
        }
    }
}
