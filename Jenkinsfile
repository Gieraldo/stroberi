pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
               echo "remote server apache"
                    sh 'ssh root@3.111.35.31 -p 22 && pwd'
                        //sh 'cd /var/www/html/stroberi && git pull'
            }
        }
    }
}
