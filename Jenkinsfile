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
		sh 'export DOCKER_HOST="ssh://dockr@10.16.90.50"'
                sh 'docker-compose up -d'
                sh 'docker-compose ps'
		sh 'unset DOCKER_HOST'
            }
        }
    }
}