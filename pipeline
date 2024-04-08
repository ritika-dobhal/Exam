pipeline {
    agent any
    tools {
        maven "maven"
        jdk "jdk21"
    }
    stages {
        stage('Stage 1 - INITIALIZATION') {
            steps {
                input('Do you want to proceed?')
                echo 'DEMO OF MAVEN PIPELINE USING JENKINS!'
            }
        }
        stage('Stage 2 - COMPILE CODE') {
            steps {
                bat "mvn compile"
            }
        }
        stage('Stage 3 - UNIT TEST') {
            steps {
                echo "Running Unit Tests"
                bat "mvn test"
            }
        }
        stage('Stage 4 - INTEGRATION TEST') {
            steps {
                echo "Running Integration Tests"
                bat "mvn verify"
            }
        }
        stage('Stage 5 - CREATE BUILD') {
            steps {
                echo "Creating a build"
                bat "mvn package"
            }
        }
    }
    post {
        failure {
            echo "Email has been sent for Jenkins build failure"
        }
    }
}
