pipeline {
  agent {
    label 'nodejs'
  }
  stages {
    stage('Install dependencies') {
      steps {
        sh 'echo \'npm ci\''
      }
    }

    stage('Check Style') {
      steps {
        sh 'echo \'npm run lint\''
      }
    }

    stage('Test') {
      steps {
        sh 'echo \'npm test\''
      }
    }

    stage('Release') {
      steps {
        sh '''
            	    oc project alzhi-greetings
            	    oc start-build greeting-console  --follow --wait
        	'''
      }
    }

  }
}