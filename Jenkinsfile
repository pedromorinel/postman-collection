pipeline {
    agent any

    stages {
        stage('Run Postman Tests') {
            steps {
                script {
                    def workspace = pwd()
                    def imageName = 'docker/dockerfile:latest'

                   
                    sh "docker run -v ${workspace}:/etc/newman --workdir /etc/newman -t ${docker/dockerfile} run api.postman_collection.json --color off --disable-unicode"
                }
            }
        }
    }
}
