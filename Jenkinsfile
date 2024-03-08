pipeline {
  agent
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactDaysToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('Hello') {
      steps {
        echo "Hello"
      }
    }
    stage('for the fix branch') {
      when {
        branch "fix-*"
      }
      steps {
        sh '''
          cat README.md
          '''
      }
    }
    stage('for the PR') {
      when {
        branch 'PR=*'
      }
      steps {
        echo ' This only runs for the PRs'
      }
    }
  }
}