pipeline {  
    agent any     
        
    stages {
        stage('Ready To Deploy') {
            steps{
                echo "ready"
            }   
        }
        
        stage('Deployment To Server akuy') {
            steps{
                echo "deploy to apache2"
                    sshagent(credentials: ['Apache2']) {
                    //sh "cd .." 
                    sh "ssh root@18.224.22.246 -p 22"
                    sh "ls"    
                    //sh "scp -r * root@18.224.22.246:/usr/local/apache2/htdocs/akuy"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                    
                 }    
            }
        }
        
    } 
}
