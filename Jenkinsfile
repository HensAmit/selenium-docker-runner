pipeline {

    agent any

    stages {
        stage('Start Grid') {
            sh "docker-compose -f grid.yaml up -d"
        }

        stage('Start Tests') {
            sh "docker-compose -f test-suites.yaml up"
        }
    }

    post {
        always {
            sh "docker-compose -f grid.yaml down"
            sh "docker-compose -f test-suites.yaml down"
        }
    }
}