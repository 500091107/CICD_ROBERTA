
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               sh '''
               aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 387731561914.dkr.ecr.eu-north-1.amazonaws.com
               docker build -t cicd_roberta .
               docker tag cicd_roberta:latest 387731561914.dkr.ecr.eu-north-1.amazonaws.com/cicd_roberta:latest
               docker push 387731561914.dkr.ecr.eu-north-1.amazonaws.com/cicd_roberta:latest
               '''
            }
        }
    }
}