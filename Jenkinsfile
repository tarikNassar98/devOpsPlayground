pipeline {
    agent any

        stages {
        stage('Build') {
           when { anyOf { branch "master"; branch "dev" } }
            steps{
           echo 'move to simple_web_server directory ...'

           sh 'cd simple_webserver'
            echo 'build NeW docker image'
            sh 'pwd'
            sh 'docker build ./simple_webserver -t image:0.0.8'
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