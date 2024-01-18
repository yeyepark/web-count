node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/yeyepark/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("yepark/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker_access_token", url: "" ]) {
        dockerImage.push()
        }
    }
}
