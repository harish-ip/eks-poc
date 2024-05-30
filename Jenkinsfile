pipeline {
    agent any

    environment {
        registry = "339712821622.dkr.ecr.eu-north-1.amazonaws.com/eks-poc-1"
    }
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', 
                   credentialsId: 'b3972f1b-1784-46d2-afef-27b5833a4683', // Replace with your credentials ID
                   url: 'https://github.com/harish-ip/eks-poc.git' // Replace with your repo URL
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }   
        // stage ("Build Image") {
        //     steps {
        //         script {
        //             docker.build registry
        //         }
        //     }
        // }
        
        // stage ("Push to ECR") {
        //     steps {
        //         script {
        //             sh "aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 339712821622.dkr.ecr.eu-north-1.amazonaws.com"
        //             sh "docker push 339712821622.dkr.ecr.eu-north-1.amazonaws.com/eks-poc-1"
                    
        //         }
        //     }
        // }
    }
}
