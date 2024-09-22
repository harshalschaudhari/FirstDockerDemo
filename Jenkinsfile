pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
                echo "Fetch Stage: The current build number is: ${env.BUILD_NUMBER}"
                 git branch: 'main', url: 'https://github.com/harshalschaudhari/FirstDockerDemo.git'
            }
        }
        stage('BuildDockerImage') {
            steps {
                bat 'dir'
                bat 'docker build -t hc-nginx:latest .'
                echo "BuildDockerImage Stage -"
            }
        }        
        stage('Tag') {
            steps {
                echo "The current build number running is: ${env.BUILD_NUMBER}"
            }
        }        
        stage('Push') {
            steps {
                //Docker Login
                //Push Docker image file
                echo "The current build number running is: ${env.BUILD_NUMBER}"
            }
        }
        stage('Deploy') {
            steps {
                 echo "Deploy stage - "
                 // Below command for Single use
                 //bat 'docker run --name hc-nginxWeb -p 8093:80 -d hc-nginx:latest'
                bat 'docker-compose -f ./docker-compose.yml up -d'
            }
        }
    }
}
