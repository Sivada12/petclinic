pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git branch: 'CI/CD', credentialsId: 'a79ed2e2-b2da-4422-9f8d-5c2febe66268', url: 'https://github.com/Sivada12/petclinic.git'
            }
        }
         stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
           stage('result') {
            steps {
                junit '**/*.xml'
            }
        }
         stage('archive') {
            steps {
                 archiveArtifacts artifacts: '**/*.jar', followSymlinks: false  
            }
        }
       
    }
}
