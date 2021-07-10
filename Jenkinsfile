node('jenkins-slave') {
    
     stage('unit-tests') {
        sh(script: """
          docker run --privileged --rm alpine /bin/sh -c "echo hello world"
        """)
    }
}
