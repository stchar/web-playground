pipeline {
  agent any
  stages {
    stage('one') {
      steps {
        checkout scm
        echo 'Hello World!'
        echo "scm = ${scm}"
        echo "env = ${env}"
        echo scm.GIT_COMMIT
        echo env.GIT_BASELINE
      }
    }
  }
}
