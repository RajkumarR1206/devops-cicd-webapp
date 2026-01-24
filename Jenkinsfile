pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t webapp:test .'
            }
        }

        stage('Run Tests in Container') {
            steps {
                sh '''
                docker run --rm webapp:test pytest
                '''
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                docker stop webapp || true
                docker rm webapp || true
                docker run -d -p 80:5000 --name webapp webapp:test
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful "
        }
        failure {
            echo "Pipeline failed "
        }
    }
}

