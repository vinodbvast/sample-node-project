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
        // stage('Test') {
        //     steps {
        //         sh "chmod +x -R ${env.WORKSPACE}"  // Change permissions recursively for the workspace
        //         sh '/home/lab001/.jenkins/workspace/Dev/Nodejs_Jenkins_Pipeline/test.sh'  // Execute your test script
        //     }
        // }
        // stage('Deliver') {
        //     steps {
        //         sh 'sudo chmod 777 ./deliver.sh'
        //         sh './deliver.sh'
        //         input message: 'Finished using the web site? (Click "Proceed" to continue)'
        //         sh 'sudo chmod 777 ./kill.sh'
        //         sh './kill.sh'
        //     }
        // }
    }
}
