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

      post {
        success {
          notifyStageEnd()
        }
        failure {
          notifyStageEnd([result: "fail"])
        }
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
