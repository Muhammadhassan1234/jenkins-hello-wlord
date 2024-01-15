pipeline {
    agent any
    parameters {
        choice(name: 'VERSION ', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'version selection')
    }
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
