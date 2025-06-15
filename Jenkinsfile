pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
                sh "checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Astutepavan/moorthy_demo_repo.git']])"
            }
        }
        stage('Build') { 
            steps {
                sh "echo 'starting building the artifacts'"
                sh "mvn clean install"
            }
        }
        // stage('Test') { 
        //     steps {
        //         // 
        //     }
        // }
        // stage('Deploy') { 
        //     steps {
        //         // 
        //     }
        // }
    }
}