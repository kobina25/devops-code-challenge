pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		    sh 'docker build -f ./frontend/ -t frontend:new .'
            }
        }
	stage('Push Docker Image to ECR') {
		steps {
			sh 'aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/a9r0i7p6'
			sh 'docker tag frontend:new public.ecr.aws/a9r0i7p6/frontend:new'
			sh 'docker push public.ecr.aws/a9r0i7p6/frontend:new'
		}
	}
        stage('Test') {
            steps {
                echo 'Testing....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		        sh 'date'
            }
        }
    }
}
