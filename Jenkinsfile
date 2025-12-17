pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/harshgbirje-h4/s3-cloudfront-website.git'
            }
        }

        stage('Upload to S3') {
            steps {
                s3Upload(
                    bucket: 'static-website-aaws',
                    workingDir: '.',
                    includePathPattern: '**/*',
                    profileName: 's3-profile'
                )
            }
        }
    }
}
