pipeline {
    agent any
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
                sh "${D} build -t abdelfattah187/app:${BRANCH_NAME} ."
                echo "Build for environment ${params.ENVIRONMENT} is successful"
            }
        }
	 stage('Test') {
            steps {
		sh "${D} run -d --name python-${BRANCH_NAME} abdelfattah187/app:${BRANCH_NAME}"
		echo "Test for environment ${params.ENVIRONMENT} is successful"
            }
        }
        stage('Deploy') {
            steps {
	        sh "${D} push abdelfattah187/app:${BRANCH_NAME}"
		echo "Deployment for environment ${params.ENVIRONMENT} is successful"
            }
        }
	stage('Cleanup') {
            steps {
		sh "${D} stop python-${BRANCH_NAME}"
		sh "${D} rm python-${BRANCH_NAME}"
		echo "Cleanup for environment ${params.ENVIRONMENT} is successful"
            }
        }
    }
}
