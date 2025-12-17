pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Upload to S3') {
            steps {
                withAWS(credentials: 'aws-creds', region: 'ap-south-1') {
                    s3Upload(
                        bucket: 'static-website-aaws',
                        path: '',
                        workingDir: '.'
                    )
                }
            }
        }
    }
}
