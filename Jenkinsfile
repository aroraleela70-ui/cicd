pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'ap-south-1'
        S3_BUCKET = 's3-demo34'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'develop', url: 'https://github.com/aroraleela70-ui/cicd.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: 'aws-jenkins-creds'
                ]]) {

                    sh '''
                    aws s3 sync . s3://$S3_BUCKET --delete
                    '''
                }
            }
        }

    }
}
