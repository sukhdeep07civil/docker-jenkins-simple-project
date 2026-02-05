pipeline{
    agent any

    stages{
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
                docker run -d -p 8086:80 myapp:1.0
                '''
            }
        }

    }
}