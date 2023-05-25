pipeline {
    agent any
    stages {
        stage('Clone repo') {
            steps {
                git url: 'https://github.com/briancowie/mea-duotask', branch: 'master'
            }
        }
    }
}
