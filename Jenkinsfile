pipeline {
    agent none

    stages {
        stage('test') {
            agent { label 'test' }
            steps {
                echo 'Deploying to TEST node...'
                checkout scm
                sh '''
                    rm -rf /var/www/html/*
                    cp -r $WORKSPACE/* /var/www/html/
                    sed -i "s/__BUILD_NUMBER__/${BUILD_NUMBER}/" /var/www/html/index.html
                    sed -i "s/__GIT_COMMIT__/$(git rev-parse --short HEAD)/" /var/www/html/index.html
                    sed -i "s/__BUILD_TIME__/$(date '+%Y-%m-%d %H:%M')/" /var/www/html/index.html
                    ls -la /var/www/html
                '''
                echo 'Deployment to TEST complete.'
            }
        }

        stage('prod') {
            agent { label 'prod' }
            steps {
                echo 'Test passed. Deploying to PROD node...'
                checkout scm
                sh '''
                    rm -rf /var/www/html/*
                    cp -r $WORKSPACE/* /var/www/html/
                    sed -i "s/__BUILD_NUMBER__/${BUILD_NUMBER}/" /var/www/html/index.html
                    sed -i "s/__GIT_COMMIT__/$(git rev-parse --short HEAD)/" /var/www/html/index.html
                    sed -i "s/__BUILD_TIME__/$(date '+%Y-%m-%d %H:%M')/" /var/www/html/index.html
                    ls -la /var/www/html
                '''
                echo 'Deployment to PROD complete.'
            }
        }
    }
}