pipeline{
	agent any 
	
    stages{
        stage("Run Tests") {
            steps {
                sh "echo SUCCESS on SPRINT"
            }
        }
        stage('Checkout') {
            steps{
                git branch: 'LIVE', credentialsId: '3cd686ab-1f5c-4dd9-9662-6ed1f11f2ef2', url: 'https://github.com/manojsubramaniam/test03.git'

            }
        }
	
	stage("build docker image"){
		     	steps {
				
				sh '''
					docker build -t nginx/nodeapp_test:latest .
					docker run -d --name nginx1234 -p 8000:80 nginx/nodeapp_test:latest
				'''
			}
		}
		

		stage("docker container"){
			steps {
				echo'running docker image into container..'
			}
		}
	stage('File Deployment'){
            steps{
                sh 'docker cp staticwebsite.html samplecont:/usr/share/nginx/html/index.html'
            }
	}
    }
}
