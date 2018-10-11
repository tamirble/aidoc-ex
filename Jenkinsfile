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
    ansiblePlaybook(
            playbook: "ansible/update_server.yml",
            credentialsId: "aidoc-aws-tamirble-key",
            inventory: "ansible/inventory/s3-sync-server/"
    )
}
