pipeline {

  environment {
    dockerimagename = "bravinwasike/react-app"
    dockerImage = ""
  }

  agent { label 'kubeagent' }

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/arunkumaruniqpro/jenkins-kubernetes-deployment.git'
      }
    }

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build dockerimagename
        }
      }
    }

    stage('Deploying React.js container to Kubernetes') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", "service.yaml")
        }
      }
    }

  }

}
