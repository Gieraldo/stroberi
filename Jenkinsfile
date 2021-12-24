pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
               echo "remote server apache"
                    sh 'ssh root@3.111.35.31:var/www/html/stroberi  -p 22 && pwd'
                        //sh 'cd /var/www/html/stroberi && git pull'
            }
        }
    }
}
