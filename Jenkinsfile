pipeline {

  // environment {
  //   registry = "192.168.1.81:5000/justme/myweb"
  //   dockerImage = ""
  // }

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/Muhammad-Imtiaz/k8s-jenkins.git', branch:'master'
      }
    }

    // stage('Build image') {
    //   steps{
    //     script {
    //       dockerImage = docker.build registry + ":$BUILD_NUMBER"
    //     }
    //   }
    // }

    // stage('Push Image') {
    //   steps{
    //     script {
    //       docker.withRegistry( "" ) {
    //         dockerImage.push()
    //       }
    //     }
    //   }
    // }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
