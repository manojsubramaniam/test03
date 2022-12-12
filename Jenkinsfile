pipeline {
    agent any
    parameters {
        choice(name: 'Docker', choices:['Docker-Container','Docker-Compose'], description: 'to refresh the list, go to configure, disable "this build has parameters", launch build (without parameters)to reload the list and stop it, then launch it again (with parameters)')
   }
    stages {
        stage('git') {
            steps {
                git branch: 'main', credentialsId: '30d20ff5-3d97-4aaa-a4da-111ae90beac8', url: 'https://github.com/manojsubramaniam/test03.git'
            }
        }
        stage('Docker Container'){
           when{ expression {env.name == 'Docker-Container'}}    
            steps {
                    sh 'docker-compose up -d --build'
            }
        }
    }
}
