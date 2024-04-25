node{
    stage('SCM checkout'){
        checkout scm
    }
    
	stage('Run Container on Dev Server'){
	def dockerRunApp = 'docker-compose up -d'
        sshagent(['dev-server']) {
	sh "ssh -o StrictHostKeyChecking=no ec2-user@35.158.125.213 ${dockerRunApp}"
     }
   }
	stage('Email Notification'){
     	 mail bcc: '', body: 'Delivery jar file is done',
	cc: '', from: '', replyTo: '', subject: 'Jenkins job', to: 'mail@example.com' 
	}
   }
}
