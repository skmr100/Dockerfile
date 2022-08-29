pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "docker build -t skmr100/docks:latest ."
                echo "image build done"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('login') {
            steps {
                sh 'sudo docker login -u "skmr100" -p "VEENA@mymom100" docker.io'
            }
        }
        stage('push') {
            steps {
                sh 'docker push skmr100/docks:latest'
            }
        }
    }
}

