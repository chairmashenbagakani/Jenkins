pipeline {
    agent any

    stages {
        stage('Checkout from GitHub') {
            steps {
                echo '📦 Pulling latest code from GitHub...'
                git(
                    url: 'git@github.com:<your-username>/simple-ec2-pipeline.git',
                    branch: 'main',
                    credentialsId: 'github-key'
                )
            }
        }

        stage('Run Code on EC2') {
            steps {
                echo '🚀 Running script on EC2 instance...'
                sh '''
                chmod +x script.sh
                ./script.sh
                '''
            }
        }
    }
}
