pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
                echo "The current build number is: ${env.BUILD_NUMBER}"
            }
        }
        stage('BuildDockerImage') {
            steps {
                echo "The current build number running is: ${env.BUILD_NUMBER}"
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
                echo "The current build number running is: ${env.BUILD_NUMBER}"
            }
        }
    }
}
