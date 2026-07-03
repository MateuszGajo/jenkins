pipeline {
    agent any 
    stages {
        stage("deploy"){
            steps { 
                 sh """
          kubectl -n local apply -f k8s-job.yaml
        """
            }
        }
    }
}