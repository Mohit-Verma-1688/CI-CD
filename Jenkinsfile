node('jenkins-slave') {
    
     stage('unit-tests') {
        sh(script: """
         sudo  docker run --rm alpine /bin/sh -c "echo hello world"
        """)
    }
}
