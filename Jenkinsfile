pipeline{
    agent any

    stages{

        stage('Cleanup old containers'){
            steps{
                bat '''
                docker rm -f $(docker ps -q) || exit 0
                '''
            }
        }



        stage('Build Docker Image'){
            steps{
                bat '''
                docker build -t myapp:1.0 .
                '''
            }
        }

        stage('Run Container'){
            steps{
                bat '''
                docker run -d -p 8085:80 myapp:1.0
                '''
            }
        }

    }
}