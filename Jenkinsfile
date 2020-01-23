pipeline {
  agent any 
  stages {
    stage('Build') {
      steps {
        sh 'tidy -e -q *.html'
      }
    }
  }
}