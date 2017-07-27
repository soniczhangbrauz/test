pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'chmod 777 $(pwd)/src/Email.php'
                sh 'cat $(pwd)/src/Email.php'
                sh 'docker run --privileged -i -v /home/sonic/jenkins/workspace/test/:/var/www/html/ -u root 6232ba0d5ba5 ls /var/www/html/'
                sh 'echo "done"'
            }
        }
    }
}