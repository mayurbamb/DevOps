pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
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
                  sourceFiles: 'dist/**',
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
