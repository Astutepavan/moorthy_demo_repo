pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
                sh "git clone 'https://github.com/Astutepavan/moorthy_demo_repo.git' "
            }
        }
        stage('Build') { 
            steps {
                sh "ech 'starting building the artifacts"
                sh "mvn install"
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