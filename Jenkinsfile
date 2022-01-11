// MODIFY THE FOLLOWING THREE LINES TO SUIT YOUR SPECIFIC PROJECT
def chatId = '-1001131394773'
def botId = '5021645900:AAFxQI0ltL5dRTNHqLfhg1Ko1ll7hUujjp8'
def validStatuses = [hudson.model.Result.FAILURE, hudson.model.Result.UNSTABLE, hudson.model.Result.SUCCESS]

def result = manager.build.result
def name = manager.build.getProject().getName()

def coverage = ''

def action = manager.build.getActions().find { it.getUrlName() == "jacoco" }
if (action != null) {
    def percentage = action.getLineCoverage().getPercentageFloat();
    def previous = action.getPreviousResult()
    if (previous) {
        def delta = percentage - previous.getLineCoverage().getPercentageFloat();
        coverage = String.format("Coverage at %.02f%% (%+.02f)", percentage, delta)
    } else {
        coverage = String.format("Coverage at %.02f%%", percentage)
    }
} else {
    manager.listener.logger.println "No coverage info available"
}

if (validStatuses.contains(result)) {
    def urlText = java.net.URLEncoder.encode("$result building $name $coverage", "utf-8")
    println new URL("https://api.telegram.org/bot$botId/sendMessage?chat_id=$chatId&text=$urlText").getText()
    
pipeline {   
    agent any    
       
    stages {
        stage('Ready To Deploy') {
            steps{
                echo "ready"
            }   
        }
        
        stage('Deployment To Server aldo') {
            steps{
                echo "deploy to apache2"
                    sshagent(credentials: ['Apache2']) {
                    sh "cd .."
                    sh "ls"
                    sh "scp -r * root@3.133.84.143:/var/www/html/stroberi"
                    //sh "ssh root@3.111.35.31 cd /var/www/html/stroberi && pwd && git pull origin master"
                    
                 }    
            }
        }
