pipeline {
    agent any

    stages {
        
        stage('Preparation') {
            steps {
                git 'https://github.com/jglick/simple-maven-project-with-tests.git'
            }
        }

        stage('Clean'){
            steps{
                bat "mvn clean"
            }
        }

        stage('test'){
            steps{
                bat "mvn test"
            }
        }

        stage('install'){
            steps{
                bat "mvn install"
            }
        }
    }
}
