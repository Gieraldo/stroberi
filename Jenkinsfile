pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh "scp -o StrictHostKeyChecking=no cd /var/lib/jenkins/workspace/Folder-Testing/testing-deploy ssh root@3.111.35.31 cd /var/www/html/stroberi"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                 }
            }
        }
    }
}
