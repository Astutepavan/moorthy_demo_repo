pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Astutepavan/moorthy_demo_repo.git']])
            }
        }
        stage('Build') { 
            steps {
                sh "echo 'starting building the artifacts'"
                sh "mvn clean install"
            }
        }
        stage('versioning') { 
            steps {
                sh "echo 'starting artifact versioning'"
                withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'awsuser', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                 sh "/usr/local/bin/aws --version "
                 sh "/usr/local/bin/aws s3 cp ./target/mavewebappdemo-2.0.0-SNAPSHOT.war s3://my-testbucket-442042510814"
               }
            }
        }
        stage('sonar') { 
            steps {
                sh "echo 'starting sonar scanning report'"
                withSonarQubeEnv('sonar') {
                sh "mvn sonar:sonar"
            }

               }
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