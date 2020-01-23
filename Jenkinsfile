pipeline{
	agent any
	stages {
		stage ('package'){
			steps{
				echo 'package....'
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
			}
		}
	}
}