pipeline {
  agent any 
  stages {
    stage('Build') {
      steps {
        sh 'tidy -e -q *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-1',credentials:'blueocean') {
          s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'c3pipelines-rotimi')
        }
      }
    }
  }
}