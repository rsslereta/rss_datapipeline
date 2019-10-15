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
                sh 'sleep 5'
			}
		}
		stage('Artifactory') {
			steps {
				echo 'Deploy to Artifactory...'
                sh 'sleep 5'
			}
		}
		stage('Composer') {
			steps {
				echo 'Trigger Composer...'
                sh 'sleep 5'
			}
		}
		stage('Develop') {
			steps {
				parallel(
					Job_Queues: {
						echo "Run job queues..."
                        sh 'sleep 5'
					},
					Parsers: {
						echo "Run parsers..."
                        sh 'sleep 5'
					}
				)
			}
		}
		stage('QA') {
			steps {
				echo 'QA Testing...'
                sh 'sleep 5'
			}
		}
		stage('Production') {
			steps {
				echo 'Deploying....'
				sh 'python --version'
                sh 'sleep 5'
			}
		}
	}
}