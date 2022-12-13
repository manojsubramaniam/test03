pipeline {
    agent any
    parameters {
        choice(name: 'Docker', choices:['Docker-Container','Docker-Compose'], description: 'to refresh the list, go to configure, disable "this build has parameters", launch build (without parameters)to reload the list and stop it, then launch it again (with parameters)')
    }
    stages {
        stage('git') {
            steps {
                git branch: 'main', credentialsId: '6fa4c8a9-14a9-44e0-8630-b540766d146d', url: 'https://github.com/manojsubramaniam/test03.git'
            }
        }
        
}
