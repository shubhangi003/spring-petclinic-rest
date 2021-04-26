pipeline {
    agent any
    stages {

        stage('Build Rest-API') {
            steps {
                sh 'nohup mvn spring-boot:run &'
                sleep(10)
            }
        }
        stage('Postman') {
            steps {
              sh 'newman run PetClinic.postman_collection.json -- environment PetClinic_Environment.postman_environment.json -- reporters junit'
            }
            post {
                always {
                    junit '**/TEST*.xml'
                }
            }

        }
        
    }
}
