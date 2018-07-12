pipeline {
    agent any
    stages {
        stage('No-op') {
            steps {
                sh 'ls'
            }
        }
    }
    post {
        always {
            mail to: 'danielle.leboeuf@exfo.com',
             subject: "Pipeline built: ${currentBuild.fullDisplayName}",
             body: "There was a build! ${env.BUILD_URL}"
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
   
}