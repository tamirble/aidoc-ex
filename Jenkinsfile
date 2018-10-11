node {
checkout([
        $class           : 'GitSCM',
        branches         : scm.branches,
        userRemoteConfigs: scm.userRemoteConfigs,
        extensions       : scm.extensions + [
                [$class: 'CleanBeforeCheckout']
        ]
])
  echo("hello")
  ansiblePlaybook("playbook.yml")
}
