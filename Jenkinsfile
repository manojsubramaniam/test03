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
                git branch: 'LIVE', credentialsId: '6fa4c8a9-14a9-44e0-8630-b540766d146d', url: 'https://github.com/manojsubramaniam/test03.git'

            }
        }
	stage('Docker Container Clean'){
            steps {
             		sh 'docker system prune -a --volumes -f'
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
