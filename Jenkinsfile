pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is build the app job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is to test the app'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is to package the app'
        sh 'npm run package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline created via code has completed...'
    }

  }
}