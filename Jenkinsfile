node {
    stage("Check out repository") {
        checkout([
                $class           : 'GitSCM',
                branches         : scm.branches,
                userRemoteConfigs: scm.userRemoteConfigs,
                extensions       : scm.extensions + [
                        [$class: 'CleanBeforeCheckout']
                ]
        ])
    }
    stage("Update server")
            {
                ansiblePlaybook(
                        playbook: "ansible/update_server.yml",
                        inventory: "ansible/inventory/s3-sync-server/",
                        credentialsId: "ec2-key-file",
                        extras: "-e 'host_key_checking=False'"
                )
            }
}