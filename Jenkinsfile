pipeline {  
    agent any   
       
    stages { 
        stage('Ready To Deploy') {
            steps{
                echo "ready"
            }
        } 
        
        stage('Deployment To Server aris') {
            steps{
                echo "deploy to apache2"
                    sshagent(credentials: ['Apache2']) {
                    sh "cd .."
                    sh "ls"
                    sh "scp -r * root@65.0.19.183:/var/www/html/stroberi"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                    
                 }    
            }
        }
        
    }
}
