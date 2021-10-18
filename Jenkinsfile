pipeline {
  agent any
  stages {
    stage('Application Build') {
      steps {
        sh '''chmod +x -R ./scripts
'''
        sh './scripts/build.sh'
      }
    }

    stage('Tests') {
      steps {
        sh './scripts/test.sh'
      }
    }

    stage('DockerImage Build') {
      steps {
        sh 'docker build -t tsepukh/myuniquebuildimage .'
      }
    }

    stage('Docker Image push') {
      steps {
        sh 'docker image push "tsepukh/myuniquebuildimage:latest"'
      }
    }

  }
}