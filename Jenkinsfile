pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'docker run -it --rm -v "$PWD":/var/www/html/ -w /var/www/html/ 6232ba0d5ba5 phpunit --bootstrap src/Email.php tests/EmailTest'
                sh 'echo "done"'
            }
        }
    }
}