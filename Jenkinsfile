node {    
    stage('Clone repository') {
        git(
          url: 'https://github.com/ppapstructure/mydiary-repo.git',
          credentialsId: 'github_access_token'
        )
    }

    stage('Build image') {
       dockerImage = docker.build("noviceuser23/mydiary-front:v3.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
