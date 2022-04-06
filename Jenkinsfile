pipeline {
    agent any
    environment  {
    cred = '352708296901.dkr.ecr.eu-central-1.amazonaws.com'
    }


        stages {
        stage('Build') {
           when { anyOf { branch "master"; branch "dev" } }
            steps{
           echo 'move to simple_web_server directory ...'

           sh 'cd simple_webserver'
            echo 'build NeW docker image'


            sh '''

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 352708296901.dkr.ecr.us-east-1.amazonaws.com
            docker build  ./simple_webserver -t simple_web_server_tarik:${BUILD_NUMBER}${BRANCH_NAME}
             docker tag simple_web_server_tarik:${BUILD_NUMBER}${BRANCH_NAME} ${cred}/simple_web_server_tarik:${BUILD_NUMBER}${BRANCH_NAME}
             docker push ${cred}/simple_web_server_tarik:${BUILD_NUMBER}${BRANCH_NAME}
                '''




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