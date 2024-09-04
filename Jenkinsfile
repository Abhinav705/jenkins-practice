pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo From Build'
            }
        }
        stage('Test') {
            steps {
                sh 'echo From test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo From Deploy'
            }
        }
    }
}