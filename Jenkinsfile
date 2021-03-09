pipeline{
    agent{
        label "jenkins-agent-node-14"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

       stage('Deploy') {
          steps {
            sh '''
              oc project airalgerie-virt-greetings
              oc start-build greeting-service --follow --wait
        '''
    }
}

    }
}
