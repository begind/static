pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-west-1', credentials:'aws-static') {
            // upload index.html to static website
            s3Upload(file:'index.html', bucket:'lucerop-udacity-static-project', path:'')
        }        
        }
     }
  }
}
