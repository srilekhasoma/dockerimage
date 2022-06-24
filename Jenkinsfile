node {
    checkout scm
	stage('registry') {
        steps {
            sh "docker login -u srilekhas -p Lekha1998"
            // sh "docker tag ${imageName} ${registryServer}/${imageName}:latest" //
            sh "docker tag srilekhas/php:latest 9492261286/php-new:latest"
            sh "docker login -u 9492261286 -p Lekha1998"
            // sh "docker push ${registryServer}/${imageName}:latest" //
            sh "docker push 9492261286/php-new:latest"
            }
        }
}	
