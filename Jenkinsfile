pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
     
        
        stage('Deploy to Tomcat Web Server') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat_server', path: '', url: 'http://98.81.238.111:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }

}
