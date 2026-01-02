@Library('Shared') _
pipeline{
    agent { label 'Agent1'}
    
    stages{
        stage("Code clone"){
            steps{
                script{
                    clone("https://github.com/raj01-25/django-notes-app.git","main")
                }
            }
        }
        stage("Code Build"){
            steps{
                script{
                    build("notes-app","latest","rajshihi")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    push("notes-app","latest","rajshihi")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    deploy()
                }
            }
        }
        
    }
}
