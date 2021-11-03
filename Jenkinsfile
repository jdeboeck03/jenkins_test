pipeline {
    parameters {
        string( name: 'MY_HOBBY', defaultValue: 'Wall Climbing', description: 'What is your favorite hobby?')
        choice( name: 'MAKE_CHOICE', choices: ['ONE', 'TWO', 'THREE', 'FOUR'], description: 'Make a choice!')
    }
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
                sh 'pytho --version'
                echo "Hello, my name is what? My name is whooo? My name is ${env.MY_NAME}"
                echo "My favorite hobby is ${params.MY_HOBBY}!"
                echo "Your choice is ${params.MAKE_CHOICE}"
            }
        }
    }
    post{
        always {
            echo "This will always run"
        }
        success {
            echo "This will only run if successful"
            echo "Also, my name is ${env.MY_NAME}"
            echo "Some Jenkins info: build number = ${env.BUILD_NUMBER} & build url = ${env.BUILD_URL}"
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