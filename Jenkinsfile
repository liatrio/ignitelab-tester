library 'LEAD'
pipeline {
  agent none
  stages {
    stage('prep') {
      agent {
        label "lead-toolchain-skaffold"
      }
      when {
          branch 'master'
      }
      steps {
        container('skaffold') {
          sh "helm --tiller-namespace=joes-staging delete --purge marketsummary"
        }
      }
    }

    stage('build solution3') {
      when {
          branch 'master'
      }
      steps {
        catchError {
          build job: 'liatrio/springtrader-marketsummary/solution3'
        }
      }
    }
    stage ('Validating solution3') {
      agent none
      when {
          branch 'master'
      }
      options {
        timeout(time: 30, unit: 'MINUTES')
      }
      input {
        message 'Continue to solution 4a'
      }
      steps {
        echo "We'll automate this check later"
      }
    }
    stage('solution 4a') {
      when {
          branch 'master'
      }
      steps {
        catchError {
          build job: 'liatrio/springtrader-marketsummary/solution4a'
        }
      }
    }
    stage ('Validating solution 4a') {
      agent none
      when {
          branch 'master'
      }
      options {
        timeout(time: 30, unit: 'MINUTES')
      }
      input {
        message 'Continue to solution 4a'
      }
      steps {
        echo "We'll automate this check later"
      }
    }
    stage('solution 4b') {
      when {
          branch 'master'
      }
      steps {
        catchError {
          build job: 'liatrio/springtrader-marketsummary/solution4b'
        }
      }
    }
    stage ('Validating solution 4b') {
      agent none
      when {
          branch 'master'
      }
      options {
        timeout(time: 30, unit: 'MINUTES')
      }
      input {
        message 'Continue to solution 4a'
      }
      steps {
        echo "We'll automate this check later"
      }
    }
    stage('solution 5') {
      when {
          branch 'master'
      }
      steps {
        catchError {
          build job: 'liatrio/springtrader-marketsummary/solution5'
        }
      }
    }
    stage('Done!') {
      when {
          branch 'master'
      }
      steps {
         echo "great success!"
      }
    }
  }
}
