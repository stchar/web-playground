semver_enabled = false
scm_enabled = false
try {
  if (scm) {
    scm_enabled = true
    println "DEBUG: before pieline step: semver = ${semver}"
  }
} catch (MissingPropertyException e) {}
try {
  if (semver) {
    semver_enabled = true
    println "DEBUG: before pieline step: semver = ${semver}"
  }
} catch (MissingPropertyException e) {}


println "DEBUG: before pieline step: env.GIT_COMMIT = ${env.GIT_COMMIT}"
println "DEBUG: before pieline step: env.GIT_BASELINE = ${env.GIT_BASELINE}"
println "DEBUG: before pieline step: env.BRANCH_NAME = ${env.BRANCH_NAME}"



pipeline {
  agent none
  stages {
    stage('one') {
      agent any
      steps {
        echo 'Hello World!'
        echo "env = ${env}"
        echo env.GIT_COMMIT
        echo env.GIT_BASELINE
        script {
          if(scm_enabled) {
            echo "scm = ${scm}"
            echo scm.getExtensions().toString()
          }
          if(semver_enabled) {
            def v = semver.parse(env.GIT_BASELINE)
            println v.nextMinorVersion()
          }
        }
      }
    }
    stage('two') {
      agent any
      steps {
        echo 'Hello World!'
        echo "env = ${env}"
        echo env.GIT_COMMIT
        echo env.GIT_BASELINE
        script {
          if(scm_enabled) {
            echo "scm = ${scm}"
            echo scm.getExtensions().toString()
          }
          if(semver_enabled) {
            def v = semver.parse(env.GIT_BASELINE)
            println v.nextMinorVersion()
          }
        }
      }
    }
  }
}
