demo:pipeline {
  agent any
  stages {
    stage('insert') {
      steps {
     	veinmindScanner([$class: 'AgentConfig', agentVersion: 'v2.0.0', ruleId: 0])
      }
    }
  }
}