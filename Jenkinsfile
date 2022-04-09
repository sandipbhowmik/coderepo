node {
    def pipeline_dir = 'ansible-deploy-pipeline'
    stage('Build') {
        dir(pipeline_dir) {
            docker.image('cytopia/ansible:2.9-tools'){
                echo "Deploying the ansiblePlaybook"
            }
        }
    }
}
