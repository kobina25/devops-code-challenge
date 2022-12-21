pipeline {
    agent any
    stages {
	stage('Clone Git Repository') {
		steps {
			sh 'git clone https://github.com/kobina25/devops-code-challenge.git ~/code'
			sh 'cd ~/code'
		}
	}
        stage('Build') {
            steps {
                echo 'Building..'
		    sh 'docker build -f ~/code/frontend/Dockerfile -t frontend:new .'
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
