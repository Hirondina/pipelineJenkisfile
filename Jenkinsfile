pipeline {
  agent any
  stage 'Checkout'
  node('slave') {
     deleteDir()
     checkout scm
}
stage 'Build & Archive Apk'
node('slave') {
  bat 'export ANDROID_SERIAL=192.168.56.101:5555 ; ./build.bat'
  step([$class: 'ArtifactArchiver', artifacts: 'meu_aplicativo/build/outputs/apk/meu_aplicativo.apk'])
 }
stage 'Run Tests'
node('slave') {
  bat 'export ANDROID_SERIAL=192.168.56.101:5555 ; ./runtests.bat'
  publishHTML(target: [reportDir: 'meu_aplicativo_testes/build/reports/androidTests/connected/', reportFiles: 'index.html', reportName: 'Testes Instrumentados'])
  step([$class: 'JUnitResultArchiver', testResults: 'meu_aplicativo_testes/build/outputs/androidTest-results/connected/*.xml']
}
