pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/musashi-13/PES1UG22CS275_Jenkins.git']]])
            } 
        }

        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS275-1 main/hello.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22CS275-1'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
