library 'LEAD'
pipeline {
  agent none
  stages {
    stage('Checkout solution3') {
      agent {
        label "lead-toolchain-skaffold"
      }
      steps {
          container('skaffold') {
              checkout([$class: 'GitSCM', branches: [[name: '*/test-solution3']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/jknight-liatrio/springtrader-marketsummary.git']]])
              sh 'ls -al'
          }
      }

    }
    stage('build solution3') {
      steps {
          build job: 'jknight-liatrio/springtrader-marketsummary/test-solution3'
      }
    }
    stage('Done') {
      agent {
        label "lead-toolchain-skaffold"
      }
      steps {
         echo "great success"
      }
    }
  }

  post {
    success {
      echo "Pipeline Success"
      notifyPipelineEnd()
    }
    failure {
      echo "Pipeline Fail"
      notifyPipelineEnd([result: "fail"])
    }
  }
}
