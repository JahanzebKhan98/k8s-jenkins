pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/JahanzebKhan98/k8s-jenkins.git', branch:'master'
      }
    }


    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }
}
