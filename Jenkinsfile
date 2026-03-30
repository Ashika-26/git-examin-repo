pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                aws s3 sync . s3://ashika-s3-pipeline \
                --delete \
                --exclude ".git/*" \
                --exclude "Jenkinsfile" \
                --exclude "README.md" \
                --exclude ".vscode/*"
                '''
            }
        }
    }
}
