demo:pipeline {
  agent any
  agent {
        docker {
            image 'golang:1.20'
        }
    }
  stages {
    stage('insert') {
      steps {
        sh '''
        go mod vendor
        go build -o main main.go
        '''
     	veinmindScanner([$class: 'AgentConfig', agentVersion: 'v2.0.0', ruleId: 0])
      }
    }
  }
}