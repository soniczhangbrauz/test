pipeline {
    agent { docker 'brauzhq-phpunit' }
    stages {
        stage('build') {
            steps {
                sh 'docker run --name 6232ba0d5ba5_$BUILD_TAG -i --rm -v jenkins_jenkins:/repo 6232ba0d5ba5 phpunit --bootstrap /repo/workspace/$(basename $WORKSPACE)/src/Email.php /repo/workspace/$(basename $WORKSPACE)/test/EmailTest.php > result.log'
            }

            post {
                success {
                echo "Build successful"
                }
                
                failure {
                    emailext (
                        subject: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                        body: """<p>FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
                            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>
                            <p>${FILE,path=result.log}</p>""",
                        to: 'sonic@brauz.com',
                        recipientProviders: [[$class: 'CulpritsRecipientProvider']]
                    )
                }
            }
        }
    }
}