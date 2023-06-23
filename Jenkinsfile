@Library('Sprints-Lib') _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
        	buildImage()
            }
        }
        stage('Push') {
            steps {
	        pushImage()
            }
        }
	stage('CleanUp') {
            steps {
	        cleanUp()
            }
        }
    }
}
