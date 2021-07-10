pipeline {

  environment {
    registry = "192.168.5.70:5000/mohit/myweb"
    dockerImage = ""
  }

 node ('jenkins-slave') {
  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/Mohit-Verma-1688/CI-CD.git'
      }
    }
   

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }

    stage('Push Image') {
      steps{
        script {
          docker.withRegistry( "" ) {
            dockerImage.push()
          }
        }
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "myweb.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }
  }
  }

}
