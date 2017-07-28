pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'docker run --name 6232ba0d5ba5_$BUILD_TAG -i --rm -v jenkins_jenkins:/repo 6232ba0d5ba5 ls /repo/workspace/test_master-YKUBYJHFWV5SAO5BKANKYXEX6RUGQUBB2GGZLHYPHNUKZELZPATQ'
                //sh 'docker run --name 6232ba0d5ba5_$BUILD_TAG -i --rm -v jenkins:/var/www/html/ 6232ba0d5ba5 phpunit --bootstrap $WORKSPACE/src/Email.php $WORKSPACE/tests/EmailTest.php'
            }
        }
    }
}