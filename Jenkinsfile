pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '6e975e35-7356-4f10-8f33-6e988dc7fa8b', path: '', url: 'http://3.141.2.200:8080')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
