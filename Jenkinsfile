pipeline {
<<<<<<< HEAD

  environment {
    registry = "192.168.5.30:5000/home/vagrant/jenkins"
    dockerImage = ""
  }

=======
>>>>>>> 8ebdc6b01417a4abc4b16b19832e8f31b893dce0
  agent any
  stages {
    stage('Checkout Source') {
      steps {
        git(url: 'https://github.com/Mohit-Verma-1688/CI-CD.git', branch: 'master', credentialsId: 'Mohit-verma-1688')
      }
    }

    stage('Build image') {
      steps {
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }

      }
    }

    stage('Push Image') {
      steps {
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
  environment {
    registry = '192.168.5.30:5000/justme/myweb'
    dockerImage = ''
  }
}