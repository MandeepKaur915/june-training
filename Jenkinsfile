pipeline {
    
    agent any

    stages {
        
       stage('checkout') {
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/MandeepKaur915/june-training.git']])
            }
        }

        stage('quality analysis'){
            steps{
                withSonarQubeEnv('Sonarqube'){
                sh "mvn sonar:sonar"
                }
            }
        }
    }
}
