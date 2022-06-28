pipeline {
        agent any
        environment {
	DOCKERHUB_CREDENTIALS=credentials('DockerHub')	
	}

        stages {
            
            stage('tag image') {
                steps {
                    sh 'docker tag srilekhas/php:latest 9492261286/php-new:latest'
                }
            }
            stage('push image') {
                steps {	
                    sh 'docker login -u 9492261286 -p Lekha1998'
                    sh 'docker push 9492261286/php-new:latest'
                }
            }
        } 
}	
