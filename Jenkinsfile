pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }

    stages {
        stage('Run Tests') {
            parallel {
                stage('Frontend Test') {
                    steps {
                        sh 'node ./frontend/test.js'
                    }
                }
                stage('Backend Test') {
                    steps {
                        sh 'node ./backend/test.js'
                    }
                }
            }
        }
    }
}

