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
			}
		}
		stage('Artifactory') {
			steps {
				echo 'Deploy to Artifactory...'
			}
		}
		stage('Composer') {
			steps {
				echo 'Trigger Composer...'
			}
		}
		stage('Develop') {
			steps {
				parallel(
					Job Queues: {
						echo "Run job queues..."
					},
					Parsers: {
						echo "Run parsers..."
					}
				)
			}
		}
		stage('QA') {
			steps {
				echo 'QA Testing...'
			}
		}
		stage('Production') {
			steps {
				echo 'Deploying....'
				sh 'python --version'
			}
		}
	}
}