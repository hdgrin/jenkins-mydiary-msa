node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/hdgrin/jenkins-mydiary-msa.git'
    }

    stage('Build image') {
       dockerImage = docker.build("hdgrin/mydiary-front:2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
