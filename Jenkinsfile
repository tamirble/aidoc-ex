node {
checkout([
        $class           : 'GitSCM',
        branches         : scm.branches,
        userRemoteConfigs: scm.userRemoteConfigs,
        extensions       : scm.extensions + [
                [$class: 'CleanBeforeCheckout']
        ]
])
  sh("ls")
  ansiblePlaybook("ansible/update_server.yml")
}
