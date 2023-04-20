pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
				echo 'Building C++ code...'
				echo 'Build Automation Tool Examples: CMake, Bazel'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Testing on C++ code...'
                echo 'Testing Automation Tool Examples: Parasoft, GTest, Catch2'
            }
			post {
				success {
					emailext to: 's222156264@deakin.edu.au',
					subject: 'Unit and Integration Testing Success - $DEFAULT_SUBJECT',
					body: '$DEFAULT_CONTENT',
					attachLog: true 
                }
				failure {
					emailext to: 's222156264@deakin.edu.au',
					subject: 'Unit and Integration Testing Failure - $DEFAULT_SUBJECT',
					body: '$DEFAULT_CONTENT',
					attachLog: true 
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis on C++ code...'
				echo 'Code Analysis Tool Examples: Clang-Tidy, cppcheck, CodeSonar'
            }
        }
        stage('Security Scan') {
            steps {
				echo 'Running code Security Scan...'
				echo 'Security Scan Tool Examples: SonarQube, Flawfinder, Coverity'
			}
			post {
				success {
					emailext to: 's222156264@deakin.edu.au',
					subject: 'Security Scan Success - $DEFAULT_SUBJECT',
					body: '$DEFAULT_CONTENT',
					attachLog: true 
                }
				failure {
					emailext to: 's222156264@deakin.edu.au',
					subject: 'Security Scan Failure - $DEFAULT_SUBJECT',
					body: '$DEFAULT_CONTENT',
					attachLog: true 
                }
            }
			
			
        }
        stage('Deploy to Staging') {
            steps {
				echo 'Deploying to Staging Server...'
				echo 'Staging Server Examples: MS Azure, DigitalOcean Droplet, Heroku' 
            }
        }
		stage('Integration Tests on Staging') {
			steps {
				echo 'Running Integration Tests on Staging Server...'
			}
			post {
				success {
					emailext to: 's222156264@deakin.edu.au',
					subject: 'Integration Testing on Staging Success - $DEFAULT_SUBJECT',
					body: '$DEFAULT_CONTENT',
					attachLog: true 
                }
			failure {
				emailext to: 's222156264@deakin.edu.au',
				subject: 'Integration Testing on Staging Failure - $DEFAULT_SUBJECT',
				body: '$DEFAULT_CONTENT',
				attachLog: true 
                }
            }	
	}
        stage('Deploy to Production') {
            steps {
				echo 'Deploying to Production Server...'
				echo 'Production Server: Heroku'
            }

        }
    }
}
