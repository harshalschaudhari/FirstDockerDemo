pipeline {
    agent any
 
    environment {
        DOCKERHUB_CREDENTIALS = credentials('hc-docker-hub')
    }
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
          stage('Login') {
          steps {
              echo "Login Stage - ${env.DOCKERHUB_CREDENTIALS_USR}"
              echo "Login Stage - ${env.DOCKERHUB_CREDENTIALS_PSW}"    
              //bat 'docker login -u  ${env.DOCKERHUB_CREDENTIALS_USR} --password-stdin'
               //sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
              //bat 'docker login -u ${env.DOCKERHUB_CREDENTIALS_USR} -p ${env.DOCKERHUB_CREDENTIALS_PSW}'
              bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
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
                bat 'docker push hc-nginx:latest'
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
