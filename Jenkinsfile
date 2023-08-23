pipeline {
    agent any

    stages {
        stage('Run Postman Tests') {
            steps {
                script {
                    def workspace = pwd()
                    def imageName = 'docker/dockerfile'

                    sh "docker run -v ${workspace}:/etc/newman --workdir /etc/newman -t ${imageName} run api.postman_collection.json --color off --disable-unicode"
                }
            }
        }
    }
}
