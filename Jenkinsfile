pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Create Artifact') {
            steps {
                sh 'mkdir -p target && echo "HW7 artifact content" > target/app.jar'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            echo 'Build completed and artifact archived successfully.'
        }
    }
}
