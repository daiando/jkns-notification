pipeline {
  agent any

  stages {
    stage('notify') {
      steps {
        echo 'Notification Time!!'
      }
    }
    post {
      success {
        emailext(
          subject: "Notification Pipeline [${env.BUILD_NUMBER}] Ran!",
          body: """<p>Notification Pipeline '[${env.BUILD_NUMBER}]' Ran!":</p>
          <p>Check console output at <a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a></p>""",
          to: "daifloss@gmail.com"
        )
      }
    }
  }
}
