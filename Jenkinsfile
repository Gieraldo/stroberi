pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh '''
                        ssh root@3.111.35.31 cd /var/www/html/stroberi && git pull -u origin master
                    '''
                 }
            }
        }
    }
}
