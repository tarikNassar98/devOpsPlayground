pipeline {
    agent any

        stages {
        stage('Build') {
            steps{
           echo 'move to simple_web_server directory ...'

           sh 'cd simple_webserver'
            echo 'build NeW docker image'
            sh 'pwd'
            sh 'docker build ./ -t image:0.0.5'
        }
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