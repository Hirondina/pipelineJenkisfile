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
        bat 'echo `Testing`'
      }
    }
    stage('Deploy') {
      steps {
        bat 'echo `Deploying`'
      }
    }
  }
}