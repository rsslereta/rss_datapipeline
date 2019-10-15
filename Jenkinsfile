pipeline {
	agent {
		docker {
			image 'python:3.5.1'
		}
	}
	stages {
		stage('build') {
			steps {
				echo 'Building..'
				sh 'python --version'
			}
		}
		stage('Develop') {
			steps {
				parallel(
					Linux: {
						echo "Test on Linux"
					},
					Windows: {
						echo "Test on Windows"
					}
				)
			}
		}
		stage('QA') {
			steps {
				echo 'Testing..'
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