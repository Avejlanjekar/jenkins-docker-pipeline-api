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
                }
            }
        }
    }
}