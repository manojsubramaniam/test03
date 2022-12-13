pipeline {
    agent any
    parameters {
        choice(name: 'Docker', choices:['Test01','Test02'], description: 'Select the Github account')
    }
    stages {
        stage('git') {
            steps {
                git branch: 'main', credentialsId: '6fa4c8a9-14a9-44e0-8630-b540766d146d', url: 'https://github.com/manojsubramaniam/test02.git'
            }
        }
    }
}
