node {
    def pipeline_dir = 'ansible-deploy-pipeline'
    stage('Build') {
        dir(pipeline_dir) {
            docker.image('cytopia/ansible:2.9-tools').inside("-e HOME=${HUDSON_HOME}"){
                echo "Deploying the ansiblePlaybook"
                git branch: 'master', url: 'git@github.com:sandipbhowmik/coderepo.git'
                ansiblePlaybook(
                    credentialsId: 'jenkins-root-sshkey',
                    inventory: 'hosts',
                    playbook: 'test-playbook.yml',
                    hostKeyChecking: false,
                )
            }
        }
    }
}
