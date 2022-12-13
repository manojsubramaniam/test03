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
                git branch: 'SPRINT', credentialsId: '30d20ff5-3d97-4aaa-a4da-111ae90beac8', url: 'https://github.com/manojsubramaniam/test03.git'

            }
        }
	stage('Docker Container Clean'){
            steps {
                sh 'docker system prune -a --volumes -f'
		sh'docker rm -f samplecont'
		sh'docker rmi -f samplecont'
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
