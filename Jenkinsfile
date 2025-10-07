pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Bindas69/hello-manual.git', branch: 'main', credentialsId: 'github-pat'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('hello-manual-image')
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    docker.image('hello-manual-image').run('-p 3090:80')
                }
            }
        }
    }
}
