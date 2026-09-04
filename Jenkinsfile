pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'develop',
                    url: 'https://github.com/ankushsurana/CICD-Deployment.git'
            }
        }

        stage('Pull Git Content') {
            steps {
                sh '''
                    mkdir -p git-content
                    cp -r * git-content/
                    echo "Git content pulled successfully."
                    ls -la git-content
                '''
            }
        }
    }
}