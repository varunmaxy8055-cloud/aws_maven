pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat 11') {
            steps {
                sh '''
                WAR_FILE=$(ls target/*.war | head -n 1)

                curl -u admin:admin -X POST \
                  -F "deploy=@$WAR_FILE" \
                  "http://15.206.164.116:8081/manager/text/deploy?path=/mywebapp&update=true"
                '''
            }
        }
    }
}
