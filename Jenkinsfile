pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/harshgbirje-h4/s3-cloudfront-website.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                s3Upload(
                    bucket: 'static-website-aaws ',
                    path: '',
                    workingDir: '.',
                    includePathPattern: '**/*'
                )
            }
        }
    }
}
