pipeline {
    agent any 
    stages {
        stage("test") {
            withCredentials([file(credentialsId: 'kubeconfig-local', variable: 'KUBECONFIG')]) {
  sh 'kubectl get nodes'
  sh 'kubectl get ns'
}
        }
        stage("deploy"){
            steps { 
                 sh """
          kubectl -n local apply -f k8s-job.yaml
        """
            }
        }
    }
}