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
                git branch: 'LIVE', credentialsId: '326769ca-039c-4630-beb1-6c6f79f78947', url: 'https://github.com/manojsubramaniam/test03.git'

            }
        }
	//stage('Docker Container Clean'){
         //   steps {
     //        		//sh'docker system prune -a --volumes -f'
	//		sh'docker rm -f samplecont'
	//		sh'docker rmi -f nginx:alpine'
	//    }
//	} 
	stage('Docker Container'){
            steps {
		sh'docker exec -it jenkins/jenkins:lts /bin/bash'
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
