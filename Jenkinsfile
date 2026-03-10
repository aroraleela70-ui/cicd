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
                scp -i /var/lib/jenkins/deploy.pem /var/lib/jenkins/workspace/demo/index.html ubuntu@15.206.163.142:/home/ubuntu/projects/index.html
                sudo systemctl reload nginx
                '''
            }
        }

    }
}
