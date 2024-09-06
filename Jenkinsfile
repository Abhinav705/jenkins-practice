pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 1, unit: 'SECONDS') 
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo From Build'
            }
        }
        stage('Test') {
            steps {
                sh 'echo From test'
                sh 'sleep 10'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo From Deploy'
            }
        }
    }
}