node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/jinah-lab/jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("k0605ja/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
