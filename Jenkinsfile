pipeline{
    agent any
    stages{
        stage ("checkout"){
            steps{
                checkout scm
            }
        }
        stage('Build Docker image'){
            steps{
                script{
                    def app= docker.build("avejlanjekar45/jenkins-docker-pipeline:${GIT_COMMIT}")
                    docker.withRegistry(
                        'https://registry.hub.docker.com',
                        'dockerhub-credentials'
                    )
                    {
                        app.push()
                    }
                }
            }
        }
    }
}