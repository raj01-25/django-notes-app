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
                build(
                        ProjectName: 'notes-app',
                        ImageTag: 'latest',
                        DockerHubUser: 'rajshihi')
            }
        }
        stage("Push to DockerHub"){
            steps{
                push("notes-app","latest","rajshihi")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
