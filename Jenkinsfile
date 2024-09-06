pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
    parameters { //like a form,taking inputs from user
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{ //set some default values and we can use them
        DEPLOY_TO =  'production'
        GREETING = 'Good Morning'
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
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo From Deploy'
            }
        }
        stage('printing params'){ //printing the inputs given by user in params block
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
                echo "testing again"    
            }
        }
    }
    post {  //executes based on whether if it is success or failure
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }
}
