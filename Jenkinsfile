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
                git branch: 'LIVE', credentialsId: 'b06c53aa-c6f1-4967-b5a0-9ff817325eb4', url: 'https://github.com/manojsubramaniam/test03.git'

            }
        }
	stage('Docker Container Clean'){
            steps {
             		//sh 'docker system prune -a --volumes -f'
			sh'docker rm -f samplecont'
			sh'docker rmi -f nginx:alpine'
	    }
	} 
	stage('Docker Container'){
            steps {
                sh 'docker-compose up -d --build'
            }
        }
	stage('File Deployment'){
            steps{
                sh 'docker cp staticwebsite.html samplecont:/usr/share/nginx/html/index.html'
            }
	}
    }
}
