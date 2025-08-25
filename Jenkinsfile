@Library("Shared") _
pipeline{
    agent {label "wsl"}
    
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/mdsarfarazalam840/django-notes-app.git", "main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app","latest","ajaysin")
                }

            }
        }
        stage("Push to Dockerhub"){
            steps{
                script{
                    docker_push("notes-app","latest","ajaysin")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
