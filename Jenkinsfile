pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'chmod 777 $(pwd)/src/Email.php'
                sh 'docker run -i --rm -v "$PWD":/var/www/html/ -w /var/www/html/ 6232ba0d5ba5 phpunit --bootstrap /var/www/html/src/Email.php /var/www/html/test/EmailTest.php'
                sh 'echo "done"'
            }
        }
    }
}