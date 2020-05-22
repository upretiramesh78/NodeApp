node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */
         git 'https://github.com/upretiramesh78/NodeApp.git'
        
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("krishnaramesh/nodeapp")
    }




	
	 stage('Upload Image to DockerHub'){
    withCredentials([string(credentialsId: 'Docker_Hub_Pwd', variable: 'password')]) {
      sh "docker login -u krishnaramesh -p ${password}"
    }
    sh 'docker push krishnaramesh/nodeapp'
 
  }
	
	
}
