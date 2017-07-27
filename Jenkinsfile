pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'chmod 777 $(pwd)/src/Email.php'
                sh 'cat $(pwd)/src/Email.php'
                sh 'docker run -i --rm -v "$PWD":/var/www/html/ -w /var/www/html/ 6232ba0d5ba5 ls'
                sh 'echo "done"'
            }
        }
    }
}