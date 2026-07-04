pipeline {
    agent any
    environment {
        KUBECONFIG_FILE = credentials('kubeconfig-local')
    }
    stages {
        stage('test') {
            steps {
                    sh 'kubectl get nodes'
                    sh 'kubectl get ns'
            }
        }
        stage('deploy') {
            steps {
                    sh '''
                            kubectl apply -f k8s-job.yaml
                    '''
            }
        }
    }
}
