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



    stage('Push image') {
        /* 
			You would need to first register with DockerHub before you can push images to your account
		*/
	  withCredentials([string(credentialsId: 'docker-hub', variable: 'password')]) {
        sh "docker login -u krishnaramesh -p Gopal@123"
        }
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
            } 
                echo "Trying to Push Docker Build to DockerHub"
    }
}
