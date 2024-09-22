pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "The current build number is: ${env.BUILD_NUMBER}"
            }
        }
        stage('Run') {
            steps {
                echo "The current build number running is: ${env.BUILD_NUMBER}"
            }
        }
    }
}
