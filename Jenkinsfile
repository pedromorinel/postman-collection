pipeline {
    agent any

    stages {
        stage('Run Postman Tests') {
            steps {
                script {
                    def workspace = pwd()
                    sh "docker run -v ${workspace}:/etc/newman --workdir /etc/newman -t postman/newman run api.postman_collection.json --color off --disable-unicode"
                }
            }
        }
    }
}
