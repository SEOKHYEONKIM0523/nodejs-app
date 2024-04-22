pipeline {
    agent { label 'agent' }

    stages { 
        stage('git scm update') {
            steps {
                git url: 'https://github.com/SEOKHYEONKIM0523/nodejs-app.git', 
                branch: 'main'
            }
        }
    
        stage('Docker build & deploy') {
            steps {
                sh 'IMAGE_NAME=SEOKHYEONKIM0523/nodejs-app docker compose build'

            }
        }
        
        stage('docker hub push') {
            steps {
                sh '''
                docker login -u tjrgusdlrk101@gmail.com -p tjrgus!@$141414
                docker push seokhyeonk/nodejsapp
                
                '''
            }
        }
        stage('microk8s run pod') {
            steps {
                sh 'microk8s kubectl run app1 --image=seokhyeonk/nodejsapp'

            }
        }
    }
}
