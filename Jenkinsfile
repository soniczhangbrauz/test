pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                //sh 'docker volume create $BUILD_TAG'
                sh 'docker run --name 6232ba0d5ba5_$BUILD_TAG -i -w /var/www/html/ 6232ba0d5ba5 ls'
                sh 'docker cp . 6232ba0d5ba5_$BUILD_TAG:/var/www/html/'
                sh 'docker exec -i 6232ba0d5ba5_$BUILD_TAG ls'
                //sh 'docker run --name  -i -v $BUILD_TAG:/var/www/html/ 6232ba0d5ba5 phpunit --bootstrap $(pwd)/src/Email.php $(pwd)/tests/EmailTest.php'
            }
        }
    }
}