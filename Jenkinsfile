pipeline {
  agent any
  stages {
    stage('Dev Build') {
      steps {
        echo 'This is Dev pipeline'
        git(url: 'https://github.com/pranikasudhakar', branch: 'Jenkins')
      }
    }

    stage('UI Automation') {
      parallel {
        stage('UI Automation') {
          steps {
            echo 'UI pipeline'
          }
        }

        stage('API Automation') {
          steps {
            echo 'API pipeline'
          }
        }

      }
    }

    stage('UAT Automation') {
      steps {
        echo 'UAT pipeline'
      }
    }

    stage('Prod Deployment') {
      steps {
        input 'Are you ok to deploy in to prod?'
      }
    }

  }
}