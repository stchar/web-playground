pipeline {
  agent any
  stages {
    stage('one') {
      steps {
        checkout scm
        echo 'Hello World!'
        echo "scm = ${scm}"
        echo "env = ${env}"
        echo env.GIT_COMMIT
        echo env.GIT_BASELINE
        echo scm.getExtensions()
      }
    }
  }
}
