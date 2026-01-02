@Library('Shared') _
pipeline{
    agent { label 'Agent1'}
    
    stages{
        stage("Code clone"){
            steps{
                scripts{
                    clone("https://github.com/raj01-25/django-notes-app.git","main")
                }
            }
        }
        stage("Code Build"){
            steps{
                scripts{
                    build("notes-app","latest","rajshihi")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                scripts{
                    push("notes-app","latest","rajshihi")
                }
            }
        }
        stage("Deploy"){
            steps{
                scripts{
                    deploy()
                }
            }
        }
        
    }
}
