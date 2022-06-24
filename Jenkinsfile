node {
    checkout scm

    stage ('Pull latest image from private-registry-1') {

    def image
    docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
        def customImage = docker.image('srilekhas/php:latest')
        customImage.pull()
    }
	}

    stage ('Push image to private-registry-2') {

    sh 'docker tag srilekhas/php:latest 9492261286/php:latest'
    image = docker.image('9492261286/php-new:latest') 
	
    }
	
    stage ('Upload Image') {
	
    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub2') {
        customImage.push()
    }
}
}	
	
