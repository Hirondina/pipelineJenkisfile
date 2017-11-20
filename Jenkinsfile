pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'echo \'make\'  archiveArtifacts artifacts: \'**/target/*.jar\', fingerprint: true '
      }
    }
    stage('Test') {
      steps {
        sh ''' bat \'make check || true\' 
 junit \'**/target/*.xml\' '''
      }
    }
    stage('Deploy') {
      steps {
        sh 'bat `make publish`'
      }
    }
  }
}