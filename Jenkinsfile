pipeline{
	agent any
	stages {
		stage ('Build'){
			steps {
				echo 'build...'
				bat 'mvn clean build'
			}
		}
		stage ('Test'){
			steps{
				echo 'test....'
				junit '**/target/*.xml'
			}
		}
		stage ('Package'){
			steps{
				echo 'package....'
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
			}
		}
	}
}