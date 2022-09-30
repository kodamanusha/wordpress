pipeline{
    agent any
    stages{
        stage('Verify Tooling'){
            steps{
                sh '''
                    docker version
                    docker info
                    docker-compose version
                    curl --version
                '''
            }
        }
        stage('Start Container'){
            steps{
                sh 'docker-compose up -d'
                sh 'docker-compose ps'
            }
        }
    }
}