pipeline {
    agent any 
    stages {
        stage("test") {
            steps {
            withCredentials([file(credentialsId: 'kubeconfig-local', variable: 'KUBECONFIG')]) {
  sh 'kubectl get nodes'
  sh 'kubectl get ns'
}
            }
        }
        stage("deploy"){
                   withCredentials([file(credentialsId: 'kubeconfig-local', variable: 'KUBECONFIG')]) {
            steps { 
                 sh """
          kubectl apply -f k8s-job.yaml
        """
            }
                   }
        }
    }
}