@Library('Shared')_
pipeline{
    agent { label "vinod"}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/shubiie/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest","shubiie")
            }
        }
        stage("Push to DockerHub"){
            steps{
                echo"Hello Shubham D"
                docker_push("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
