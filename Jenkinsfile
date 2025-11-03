pipeline {
    agent any

    environment {
        EC2_INSTANCE = "your-ec2-instance"
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                echo "📦 Pulling latest code from GitHub..."
                git branch: 'master',
                    url: 'https://github.com/chairmashenbagakani/Jenkins.git',
                    credentialsId: 'github-token'
            }
        }

        stage('Build') {
            steps {
                echo "🏗️ Building application..."
                sh 'echo "Build step executed successfully."'
            }
        }

        stage('Run Code on EC2') {
            steps {
                echo "🚀 Running code on EC2..."
                sh 'echo "Deploying to EC2 instance..."'
            }
        }

        stage('Post-Build Actions') {
            steps {
                echo "✅ Pipeline completed successfully."
            }
        }
    }

    post {
        failure {
            echo "❌ Build failed. Check Jenkins console logs for more info."
        }
    }
}
