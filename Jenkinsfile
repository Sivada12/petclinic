node() {
    stage('checkout') {
        echo 'Checking out in Development Branch!!'
        git 'https://github.com/Sivada12/petclinic.git'
    }

    stage('build') {
        echo 'Building out  in Development Branch!!'
        env.PATH = "C:/Program Files/Maven/apache-maven-3.9.9/bin;c:\\windows\\system32"
        bat 'mvn package'
    }

    stage('archiving') {
        echo 'Archiving out  in Development Branch !!'
        archiveArtifacts artifacts: 'target/*.war'
    }
    
    stage('post') {
        echo 'Pipeline finished  in Development Branch'
        step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/*.xml'])
    }
}
