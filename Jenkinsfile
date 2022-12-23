pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https: //github.com/WorkshopsByKhaja/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t 8465824520/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push 8465824520/saleor:DEV'
            }
        }
        stage('terraform') {
            steps {
                git clone https: //github.com/hashicorp/learn-terraform-provision-eks-cluster
                    sh.'terraform init'
                    sh. 'terraform apply --auto-approve'
            }
        }
    }
}
