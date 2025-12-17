pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'eu-north-1'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to S3') {
            steps {
                withAWS(credentials: 'aws-s3-credentials', region: 'eu-north-1') {
                    s3Upload(
                        bucket: 'static-website-aaws',
                        workingDir: '.',
                        includePathPattern: '**/*'
                    )
                }
            }
        }
    }
}
