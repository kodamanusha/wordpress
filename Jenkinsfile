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
                sh 'docker -H dockr@10.16.90.50 docker-compose up -d'
                sh 'docker -H dockr@10.16.90.50 docker-compose ps'
            }
        }
    }
}