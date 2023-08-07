demo:pipeline {
    agent {
        docker {
            image 'golang:1.20'
        }
    }
    options {
        timeout(time: 20, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    stages {
        stage('build') {
        steps {
            sh '''
            go mod vendor
            go build -o main main.go
            '''
        }
    }
    stage('scan') {
      steps {
     	veinmindScanner([$class: 'AgentConfig', agentVersion: 'v2.0.0', ruleId: 0])
      }
    }
  }
}