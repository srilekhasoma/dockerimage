node {
    checkout scm

    stage 'Pull latest image from private-registry-1'

    def image
    docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
        image = docker.image('srilekhas/php:latest')
        dockerImage.pull()
    }

    stage 'Push image to private-registry-2'

    // SOLUTION START
    sh 'docker tag srilekhas/php:latest 9492261286/php:latest'
    image = docker.image('9492261286/php:latest') 
    // SOLUTION END

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub2') {
        image.push()
    }
}
