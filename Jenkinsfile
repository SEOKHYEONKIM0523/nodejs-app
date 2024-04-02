pipeline {
    agent any

    stages {
        stage('git scm update') {
            steps {
                git url: 'https://github.com/SEOKHYEONKIM0523/nodejs-app.git', 
                branch: 'main'
            }
        }
    
        stage('Docker build & deploy') {
            steps {
                sh '''
                docker compose up --build -d
                '''
            }
        }
    }
}
