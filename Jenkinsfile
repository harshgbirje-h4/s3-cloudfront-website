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
                s3Upload(
                    bucket: 'static-website-aaws',
                    workingDir: '.',
                    includePathPattern: '**/*'
                )
            }
        }
    }
}
