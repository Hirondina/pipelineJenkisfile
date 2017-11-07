pipeline {
  agent any
  stages {
    stage('Biuld') {
      steps {
        git 'https://github.com/Hirondina/pipelineJenkisfile.git'
      }
    }
    stage('Test') {
      steps {
        sh 'echo `Testing`'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo `Deploying`'
      }
    }
  }
}