pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "echo 'npm ci'"
            }
        }

        stage("Check Style"){
            steps{
                sh "echo 'npm run lint'"
            }
        }

        stage("Test"){
            steps{
                sh "echo 'npm test'"
            }
        }

        // Add the Release stage here
	stage('Release') {
    	    steps {
        	sh '''
            	    oc project ygscya-greetings
            	    oc start-build greeting-console  --follow --wait
        	'''
    }
}
    }
}
