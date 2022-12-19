pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/WorkshopsByKhaja/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t 8465824520/image:tagname' .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker push 8465824520/image:tagname'
            }
        }
    }
}
