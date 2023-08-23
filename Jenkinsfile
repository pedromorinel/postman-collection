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
    stage('Clone Repository') {
        steps {
        git branch: 'main', credentialsId: 'thiagolazzarotto', url: 'https://github.com/pedromorinel/postman-collection'
    }
} 

    stage('Debug') {
        steps {
            sh 'ls -la /var/jenkins/workspace/sandbox/sandbox-morinel-qa'
        }
    }
        
    stage('Run Postman Collection') {
        steps {
            sh 'newman run /etc/newman/api.postman_collection.json
            }
        }
    }
}
