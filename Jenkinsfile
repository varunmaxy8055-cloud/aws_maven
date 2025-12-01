pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing (no real tests yet)...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage placeholder (Tomcat later)'
            }
        }
    }
}
