pipeline {

  environment {
    dockerimagename = "bayesimpact/react-base"
    dockerImage = ""
  }

  agent { label 'kubeagent' }

  stages {
    stage('Deploying React.js container to Kubernetes') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", "service.yaml")
        }
      }
    }

  }

}
