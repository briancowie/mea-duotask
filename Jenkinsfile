pipeline {
    agent any
    stages {
        stage('Clone repo') {
            steps {
                git url: 'https://github.com/briancowie/mea-duotask', branch: 'master'
            }
        stage('Build and run container'){
            steps { 
                sh '''
                docker network create duo-task-net
                docker build -t duo-task:v1
                docker run -d --network duo-net --name duo-task duo-task:v1
                docker run -d -p 80:80 --mount type=bind,source=$(pwd)/nginx.conf,target=/etc/nginx/nginx.conf --network duo-net --name nginx nginx:alpine
            }
        }
    }
}
