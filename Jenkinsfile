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
            inventory: "ansible/inventory/s3-sync-server/",
            credentialsId: "ec2-key-file"
    )
}

