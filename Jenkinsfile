pipeline {
	agent {
		docker {
			image 'python:3.5.1'
		}
	}
	stages {
		stage('build') {
			steps {
				echo 'Building...'
				sh 'python --version'
                sh 'sleep 3'
			}
		}
		stage('Artifactory') {
			steps {
				echo 'Deploy to Artifactory...'
                sh 'sleep 3'
			}
		}
		stage('Composer') {
			steps {
				echo 'Trigger Composer...'
                sh 'sleep 3'
			}
		}
		stage('Develop') {
			steps {
				parallel(
					Job_Queues: {
						echo "Run job queues..."
                        sh 'sleep 3'
					},
					Parsers: {
						echo "Run parsers..."
                        sh 'sleep 3'
					}
				)
			}
		}
		stage('QA') {
			steps {
				echo 'QA Testing...'
                sh 'sleep 3'
			}
		}
		stage('Production') {
			steps {
				echo 'Deploying....'
                sh 'sleep 3'
			}
		}
	}
}