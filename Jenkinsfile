pipeline {
    agent any
    parameters {
        string(name: 'GREETING', defaultValue: 'Hello', description: 'The greeting message')
        choice(name: 'BRANCH', choices: ['master', 'dev'], description: 'Branch to build')
    }
    stages {
        stage('Example') {
            steps {
                echo "${params.GREETING}, we are building the ${params.BRANCH} branch."
            }
        }
    }
}

pipeline {
    agent any
    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Czy uruchomić etap wdrożenia?')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building applications...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing Applications...'
            }
        }
        stage('Deploy') {
            when {
                expression { params.DEPLOY }
            }
            steps {
                echo 'Implementing applications...'
            }
        }
    }
}
