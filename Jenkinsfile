pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ hello.cpp -o hello'
            }
        }
        stage('Run') {
            steps {
                sh './hello'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'hello', allowEmptyArchive: true
        }
        failure {
            echo 'Build or Run stage failed!'
        }
    }
}
