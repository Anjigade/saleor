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
                sh 'docker image build -t anjigade/saleor-core:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push anjigade/saleor-core:DEV'
            }
        }
    }
}