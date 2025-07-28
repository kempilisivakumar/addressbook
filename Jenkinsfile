pipeline {
    agent any
    parameters {
  string defaultvalue: '10', name: 'BUILD_NO'
}
    stages {
        stage('Compile') {
            steps { 
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps { 
                sh 'mvn test'
            }
        }
        stage('package') {
            steps { 
                sh 'mvn package'
                archiveArtifacts artifacts: 'Dockerfile', followSymlinks: false
            }
        }
    }
}
