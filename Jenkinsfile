pipeline {
    agent any
    stages {

        stage('Build Rest-API') {
            steps {
                sh 'nohup mvn spring-boot:run &'
                sleep(10)
            }PetClinic.postman_collection.json
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
        stage('Build Angular') {
              steps {
                sh 'curl https://jcenter.bintray.com/com/athaydes/rawhttp/rawhttp-cli/1.0/rawhttp-cli-1.0-all.jar -o rawhttp.jar && nohup java -jar ./rawhttp.jar serve . -p 4200 &'
                sleep(10)  
              }
        }
    }
}
