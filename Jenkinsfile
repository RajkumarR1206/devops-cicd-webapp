pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t webapp:v1 .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                docker stop webapp || true
                docker rm webapp || true
                docker run -d -p 80:5000 --name webapp webapp:v1
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful 🚀"
        }
        failure {
            echo "Pipeline failed ❌"
        }
    }
}
