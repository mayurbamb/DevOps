pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        // nothing to build for a simple HTML application
      }
    }
    stage('Test') {
      steps {
        // no automated tests for a simple HTML application
      }
    }
    stage('Deploy') {
      steps {
        sshPublisher(
          publishers: [
            sshPublisherDesc(
              configName: 'my-ssh-server',
              transfers: [
                sshTransfer(
                  sourceFiles: '**/*',
                  remoteDirectory: '/var/www/html'
                )
              ]
            )
          ]
        )
      }
    }
  }
}
