pipeline {
    environment {
        MY_NAME = 'Jelle'
    }
    agent {
        docker {
            image "python:latest"
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                echo "Hello, my name is what? My name is whooo? My name is ${MY_NAME}"
            }
        }
    }
    post{
        always {
            echo "This will always run"
        }
        success {
            echo "This will only run if successful"
            echo "Also, my name is ${MY_NAME}"
        }
        failure {
            echo "This will only run if failed"
        }
        unstable {
            echo "This will only run if the run was marked as unstable"
        }
        changed {
            echo "This will only tun if the state of the Pipeline has changed"
            echo "For example, if te Pipeline was previously failing but is now successfull"
        }
    }
}