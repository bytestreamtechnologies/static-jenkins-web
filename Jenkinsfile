pipeline{
    agent any
    environment {
        AWS_DEFAULT_REGION    = "ap-south-1"
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages{
        stage('deploy'){
            steps{
                sh "aws configure set region $AWS_DEFAULT_REGION" 
                sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
                sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
                sh "aws s3 cp src/index.html s3://sonu-static-web"
            }
        }
    }

}

