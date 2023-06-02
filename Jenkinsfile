pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/ArmyCPUDan91/flasking.git', branch: 'main')
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t dmoore31/flask app .'
      }
    }

    stage('Docker login/ shell script') {
      steps {
        sh 'docker login -u dmoore31 -p dckr_pat_05apnqMpur69MafcId_taFwAG6Q'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push dmoore31/flask_app'
      }
    }

  }
}