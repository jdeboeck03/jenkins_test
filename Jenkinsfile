pipeline {
    agent {
        docker {
            image 'python:latest'
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
    post{
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will only run if successful'
        }
        failure {
            echo 'This will only run if failed'
        }
        unstable {
            echo 'This will only run if the run was marked as unstable'
        }
        changed {
            echo 'This will only tun if the state of the Pipeline has changed'
            echo 'For example, if te Pipeline wwas previously failing but is now successfull'
        }
    }
}