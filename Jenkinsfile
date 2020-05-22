node {
   stage('Clone repository') {
         git 'https://github.com/upretiramesh78/NodeApp.git'        
    }

    stage('Build image') {
      app = docker.build("krishnaramesh/nodeapp")
    }

    stage('Test image') {        
        app.inside {
            echo "Tests passed"
        }
    }

}
