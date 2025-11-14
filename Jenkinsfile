pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat 9') {
            steps {
                sh '''
                WAR_FILE=target/mywebapp.war

                curl -u admin:admin "http://15.206.164.116:8081/manager/text/undeploy?path=/mywebapp"

                curl -u admin:admin -T $WAR_FILE "http://15.206.164.116:8081/manager/text/deploy?path=/mywebapp&update=true"
                '''
            }
        }
    }
}
15.206.164.116
