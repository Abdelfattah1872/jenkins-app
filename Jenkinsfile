pipeline {
    agent {label 'AWS-ins'}
    environment {
        D = 'docker'
    }
    parameters {
        string(name: 'ENVIRONMENT', defaultValue: 'dev', description: 'Environment to deploy')
        booleanParam(name: 'CLEAN_BUILD', defaultValue: true, description: 'Perform a clean build')
    }

    stages {
        stage('Build') {
            
            steps {
		    
                echo "Build for environment ${params.ENVIRONMENT} is successful"
            }
        }
	 stage('Test') {
            steps {
		echo "Test for environment ${params.ENVIRONMENT} is successful"
            }
        }
        stage('Deploy') {
            steps {
		echo "Deployment for environment ${params.ENVIRONMENT} is successful"
            }
        }
	stage('Cleanup') {
            steps {
		echo "Cleanup for environment ${params.ENVIRONMENT} is successful"
            }
        }
    }
}
