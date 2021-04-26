pipeline {
    agent any
    stages {

        stage('Build Rest-API') {
            steps {
                sh 'cd spring-petclinic-rest-master/spring-petclinic-rest-master -- mvn spring-boot:run'
            }
        }
    }
}
