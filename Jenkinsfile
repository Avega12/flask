pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/Avega12/flask.git', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t avega12/flask_app .'
      }
    }

    stage('docker login') {
      steps {
        sh 'docker login -u avega12 -p 779d99ae-8751-4211-9393-a27c834ce959'
      }
    }

    stage('docker push') {
      steps {
        sh 'docker push avega12/flask_app'
      }
    }

  }
}