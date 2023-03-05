pipeline {
    agent any
    parameters {
        string(name: 'Person', defaultValue: 'Abhay Singh', description: 'Who are you')
        booleanParam(name: 'isMale', defaultValue: 'true', description: '')
        choice(name: 'City', choices: ['Gaya','Patna','Nalanda'], description: '')
    }
    stages {
        stage('Parameters') {
            steps {
                sh 'echo ${Person}'
                sh 'echo ${isMale}'
                sh 'echo ${City}'
            }
        }
        stage('Test') {
            steps {
                echo 'Test is in progress'
            }
        }
        stage('Build') {
            steps {
                echo 'Build is in progress'
            }
        }
        stage('Deploy-Test') {
            steps {
                echo 'Deploying on Test Server'
            }
        }
        stage('Continue ?') {
            input {
                message 'Should we continue?'
                ok 'Yes we should'
            }
            steps {
                echo 'Deploying on Production Server'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo "Failure"
        }
        success {
            echo "Success"
        }    
    }
}
