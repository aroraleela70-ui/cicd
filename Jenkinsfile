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
                cp index.html /home/ubuntu/projects/
                sudo systemctl reload nginx
                '''
            }
        }

    }
}
