pipeline {
  agent any
  stages {
    stage('one') {
      steps {
        echo 'Hello World!'
        echo "scm = ${scm}"
        echo "env = ${env}"
        echo scm.GIT_COMMIT
        echo scm.GIT_BASELINE
      }
    }
  }
}
