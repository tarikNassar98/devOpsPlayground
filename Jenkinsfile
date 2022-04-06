pipeline {
    agent any

    stages {
        stages {
        stage('Build') {
           echo 'move to simple_web_server directory ...'
            sh 'cd simple_webserver'
            echo 'build NeW docker image'
            sh 'docker build dockerfile -t image:0.0.5'
        }
        stage('Test') {
            steps  {
                echo 'Testing. .'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}