
pipeline {
    agent any

    environment {

    
        REGISTRY_URL = '387731561914.dkr.ecr.eu-north-1.amazonaws.com'
    }

    stages {
        stage('Build') {
            steps {
               sh '''
               aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 387731561914.dkr.ecr.eu-north-1.amazonaws.com
               docker build -t cicd_roberta .
               docker tag cicd_roberta:latest $REGISTRY_URL /cicd_roberta:latest
               docker push $REGISTRY_URL/cicd_roberta:latest
               '''
            }
        }
    }
}