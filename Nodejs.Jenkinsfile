pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/dev']], userRemoteConfigs: [[url: 'https://github.com/vinodbvast/sample-node-project.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'sudo chmod -S 777 ./test.sh'
                sh './test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh 'sudo chmod -S 777 ./deliver.sh'
                sh './deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'sudo chmod -S 777 ./kill.sh'
                sh './kill.sh'
            }
        }
    }
}
