pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'develop',
                    url: 'YOUR_GIT_REPOSITORY_URL'
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