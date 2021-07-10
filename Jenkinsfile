node('jenkins-slave') {
    
     stage('unit-tests') {
        sh(script: """
          docker run --privileged -v /var/run/docker.sock:/var/run/docker.sock --rm alpine /bin/sh -c "echo hello world"
        """)
    }
}
