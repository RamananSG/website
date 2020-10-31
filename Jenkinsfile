pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                build 'Test'
            }
        }
        stage('Test') {
            steps {
                build 'Testurl'
            }
        }
        stage('hub-push') {
            steps {
                build 'DockerPush'
            }
        }
        stage('Prod') {
            when {
                branch 'master' 
            }
            steps {
                build 'Prod'
            }
        }
    }
}
