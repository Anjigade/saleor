pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/Anjigade/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t Anjigade/saleor-core:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push Anjigade/saleor-core:DEV'
            }
        }
    }
}