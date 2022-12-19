pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/sandeepreddygurram/salcor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t 8465824520/salcor-dashboard:tagname .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push 8465824520/salcor-dashboard:tagname'
            }
        }
    }
}
