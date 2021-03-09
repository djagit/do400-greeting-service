pipeline{
    agent any

    stages{
        stage('Deploy') {
            steps {
                sh '''
                    oc project airalgerie-virt-deploy-strategies
                    oc start-build greeting-service --follow --wait
                '''
            }
        }
    }
}
