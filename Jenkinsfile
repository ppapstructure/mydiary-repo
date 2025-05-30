node {    
    stage('Clone repository') {
        git(
          url: 'https://github.com/ppapstructure/jenkins-mydiary-msa.git',
          credentialsId: 'github_access_token'
        )
    }

    stage('Build image') {
       dockerImage = docker.build("noviceuser23/mydiary-front:v2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
