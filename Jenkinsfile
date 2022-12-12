pipeline {
    agent any
    parameters {
        choice(name: 'Docker', choices:['Docker-Container','Docker-Compose'], description: 'to refresh the list, go to configure, disable "this build has parameters", launch build (without parameters)to reload the list and stop it, then launch it again (with parameters)')
   }
    stages {
        stage('git') {
            steps {
                git branch: 'main', credentialsId: '0f902933-219b-40f5-ba89-504c8081218d', url: 'https://github.com/Arunkumar1120/Test_Jenkins.git'
            }
        }
      when {
               expression { params.name == 'Docker-Container' }
          } 
          {
          stage('Docker Container'){
            steps {
                sh 'docker-compose up -d --build'
            }
        }
    }
}
