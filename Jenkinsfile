pipeline {
     agent any
     stages {
         stage('Upload to AWS') {
             steps {
                 withAWS(credentials: 'aws-static') {
                     s3Upload(file: 'index.html', bucket: 'static-udacity-aws-app')
                 }
             }
         }

         stage('Linting') {
             steps {
                 tidy -q -e *.html
             }
         }
     }
}
