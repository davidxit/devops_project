pipeline {
    agent any

    stages {
       
        stage('MVN BUILD') {
            steps {
                sh "mvn clean package"
            }
        }
        
         stage('DOCKER IMAGE') {
            steps {
                sh "docker build -t localhost:5000/mojobraz:v${env.BUILD_ID} ."
                sh "docker push localhost:5000/mojobraz:v${env.BUILD_ID}"                
            }
        }
        
          stage('SAVE BUILD ID') {
            steps {
                sh "echo 'v${env.BUILD_ID}' > build_id"
                sh "scp build_id vagrant@172.42.42.100:/home/vagrant"                
            }
        }
        
    }
}
