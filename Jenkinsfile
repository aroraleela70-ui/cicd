pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/aroraleela70-ui/cicd.git'
            }
        }

        stage('Deploy to Server') {
            steps {
                sh '''
                cp $WORKSPACE/index.html /home/ubuntu/projects/index.html
                sudo systemctl reload nginx
                '''
            }
        }

    }
}
