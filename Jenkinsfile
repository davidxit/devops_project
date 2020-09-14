pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                git "https://github.com/davidxit/devops_project.git"
            }
        }
        
        stage('MVN BUILD') {
            steps {
                sh "mvn clean package"
            }
        }
        
         stage('DOCKER IMAGE') {
            steps {
                sh "docker build -t obraz:v1"
            }
        }
        
    }
}
