pipeline {
    agent any

    stage('Clone Repository') {
    steps {
        git branch: 'main', credentialsId: 'thiagolazzarotto', url: 'https://github.com/pedromorinel/postman-collection'
    }
} 
    stages {
        stage('Run Postman Tests') {
            steps {
                sh 'docker run -t postman/newman run -h' 
                sh 'docker run -v ${WORKSPACE}:/etc/newman --workdir /etc/newman -t postman/newman run api.postman_collection.json --color off --disable-unicode'
            }
        }
    }
}
