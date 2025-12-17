pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to S3') {
            steps {
                s3Upload(
                    bucket: 'static-website-aaws',
                    profileName: 'jenkinsdeploy',
                    workingDir: '',
                    includePathPattern: '**/*'
                )
            }
        }
    }
}

