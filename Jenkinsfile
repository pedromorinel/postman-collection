pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install -g newman'
                }
            }
        }
        stage('Run Postman Collection') {
            steps {
                sh 'newman run /etc/newman/api.postman_collection.json
            }
        }
    }
}
