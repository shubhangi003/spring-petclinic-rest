pipeline {
    agent any
    stages {

        stage('Build Rest-API') {
            steps {
                sh 'nohup mvn spring-boot:run &'
                sleep(10)
            }
        }
    }
}
