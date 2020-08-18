pipeline {
     agent any
     stages {
         stage('Build') {
              steps {
                  sh 'echo Building...'
              }
         }
         stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
         stage('Build Docker Image') {
              steps {
                  sh 'docker build -t capstone-project-cloud-devops .'
              }
         }
         stage('Push Docker Image') {
              steps {
                  sh 'echo Image Push...'
                  }
         }
         stage('Deploying') {
              steps{
                  echo 'Deploying to AWS...'
                  echo '+ kubectl apply -f rolling.json '
              }
        }
        stage("Cleaning up") {
              steps{
                    echo 'Cleaning up app...'
                    sh "docker system prune"
              }
        }
     }
}
