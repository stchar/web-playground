semver_enabled = false
scm_enabled = false
println "DEBUG: before pieline step: env.GIT_COMMIT = ${env.GIT_COMMIT}"
println "DEBUG: before pieline step: env.GIT_BASELINE = ${env.GIT_BASELINE}"
println "DEBUG: before pieline step: env.BRANCH_NAME = ${env.BRANCH_NAME}"
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
          if(semver_enabled) {
            def v = semver.parse(env.GIT_BASELINE)
            println v.nextMinorVersion()
          }
        }
      }
    }
  }
}
