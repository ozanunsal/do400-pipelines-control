pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }

    parameters {
        booleanParam(name: "RUN_FRONTEND_TESTS", defaultValue: true)
    }

    stages {
        stage('Run Tests') {
            parallel {
                stage('Frontend Test') {
                    when { expression { params.RUN_FRONTEND_TESTS } }
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

