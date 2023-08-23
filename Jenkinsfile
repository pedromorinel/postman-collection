pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Clonar o repositório GitHub
                    git branch: 'main', credentialsId: 'thiagolazzarotto', url: 'https://github.com/pedromorinel/postman-collection'
                }
            }
        }
    
    stage('Debug') {
    steps {
        sh 'ls -la /var/jenkins/workspace/sandbox/sandbox-morinel-qa'
    }
}

        
        stage('Run Postman Tests') {
            steps {
                script {
                    // Executar os testes usando Docker e Newman
                    sh 'docker run -v ${WORKSPACE}:/etc/newman --workdir /etc/newman -t postman/newman run api.postman_collection.json --color off --disable-unicode'
                }
            }
        }
    }
}
