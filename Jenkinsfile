pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''bat \'make\' 
archiveArtifacts artifacts: \'**/target/*.jar\', fingerprint: true 
'''
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