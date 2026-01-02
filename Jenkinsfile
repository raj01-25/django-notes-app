@Library('Shared')_
pipeline{
    agent { label 'Agent1'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
                clone("https://github.com/raj01-25/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
                build("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                push("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
