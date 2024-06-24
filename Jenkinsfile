println "DEBUG: before pieline step env.GIT_COMMIT = ${env.GIT_COMMIT}"
println "DEBUG: before pieline step env.GIT_BASELINE = ${env.GIT_BASELINE}"

pipeline {
  agent any
  stages {
    stage('one') {
      steps {
        echo 'Hello World!'
        echo "scm = ${scm}"
        echo "env = ${env}"
        echo env.GIT_COMMIT
        echo env.GIT_BASELINE
        echo scm.getExtensions().toString()
        script {
          def v = semver.parse(env.GIT_BASELINE)
          println v.nextMinorVersion()
        }
      }
    }
  }
}
