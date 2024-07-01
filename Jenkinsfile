node ('Application'){  
     def app
     stage('Cloning Git') {
         /* Let's make sure we have the repository cloned to our workspace */
        checkout scm
     }  
    
    // stage('Build-and-Tag') {
    // /* This builds the actual image; synonymous to
    //      * docker build on the command line */
    //     app = docker.build("rocketmario/rocket92")
    // }

        stage('Build-and-Tag') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        sh 'sudo docker build -t rocketmario/rocket92 .'
        app = "rocketmario/rocket92"
    }
    
    // stage('Post-to-dockerhub') {
    
    //  docker.withRegistry('https://registry.hub.docker.com', 'training') {
    //         app.push("latest")
    //     			}
    //      }
  
    stage('Post-to-dockerhub') {
        sh "sudo docker login"
        sh "sudo docker push ${app}:latest"
    }

<<<<<<< HEAD
    
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line */
        app = docker.build("amrit96/snake")
    }
    stage('Post-to-dockerhub') {
    
     docker.withRegistry('https://registry.hub.docker.com', 'training_creds') {
            app.push("latest")
         }
    stage('SECURITY-IMAGE-SCANNER'){
        build 'SECURITY-IMAGE-SCANNER-AQUAMICROSCANNER'
    }
  
    
=======
>>>>>>> 1f0142fd2778ec831041b3c328ea2b438a3414e7
    stage('Pull-image-server') {
    
         sh "sudo docker compose down"
         sh "sudo docker compose up -d"	
      }
 
}
