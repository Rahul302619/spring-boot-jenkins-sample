pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                credentialsId: 'git-hub-credentials',
                url: 'https://github.com/Rahul302619/spring-boot-jenkins-sample.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Build get triggered......'
                bat 'mvn clean install -DskipTests'
            }
        }
        stage('Test') {
            steps {
                echo 'Test get triggered......'
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy get triggered......'

                //run springboot application in attached mode
                 bat 'mvn spring-boot:run'

                 //sh 'nohup ./mvnw spring-boot:run -Dserver.port=8001 &' -> for detach mode
            }
        }
    }
}