pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }

    stages {
        stage ('clean Stage') {

            steps {
                    sh 'mvn clean'
                
            }
        }

        stage ('Testing Stage') {

            steps {
                    sh 'mvn test'
                
            }
        }


        stage ('build Stage') {
            steps {
                    sh 'mvn install'
                
            }
            deploy adapters: [tomcat8(path: '', url: 'http://ec2-15-206-123-46.ap-south-1.compute.amazonaws.com:8090/')], contextPath: null, war: '/target/WebApp.war'
        }
    }
}
