pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                sh 'docker build -t mayur-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop mayur-container || true
                docker rm mayur-container || true
                docker run -d -p 8085:80 --name mayur-container mayur-app
                '''
            }
        }
    }
}
