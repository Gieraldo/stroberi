pipeline {
    agent any 
      
    stages {
        stage('Remote SSH') {
            steps{
                echo "remote server apache"
                sshagent(credentials: ['Apache2']) {
                    sh "scp -p root@15.207.254.161:/var/lib/jenkins/workspace/Folder-Testing/testing-deploy root@3.111.35.31:/var/www/html/stroberi"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                 }
            }
        }
    }
}
