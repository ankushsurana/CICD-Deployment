pipeline {
    agent any

    stages {
        stage('Pull Git Content') {
            steps {
                dir('git-content') {
                    git branch: 'develop',
                        url: 'https://github.com/ankushsurana/CICD-Deployment.git'
                }
                echo 'Git content pulled successfully.'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -la git-content'
            }
        }
    }
}