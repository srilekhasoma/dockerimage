pipeline {
        agent any
        }
        environment {
	DOCKERHUB_CREDENTIALS=credentials('DockerHub')	
	def jobName = currentBuild.fullDisplayName
	def mailToRecipients = 'somasrilekha98@gmail.com'
	def useremail = 'somasrilekha98@gmail.com'	
	}	
        stages {
            
            stage('tag image') {
		    
		  // starts here//  
		 def userAborted = false   
		 emailext body: '*'
		 // Please go to console output of ${BUILD_URL}input to approve or Reject.<br>
		 '*'
		 mimeType: 'test/html'   
                 subject: "[Jenkins] ${jobName} Build Approval Request",
		 from: "$(useremail)",	 
                 to: "$(mailToRecipients)",
		 recipientProviders: [[$class: 'CulpritsRecipientProvider']]
			 
                 body: '''<a href="${BUILD_URL}input">click to approve</a>'''    
		    // ends here //
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
