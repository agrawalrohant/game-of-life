pipeline{
	agent any
	stages {
		stage ('package'){
			steps{
				echo 'package....'
				sh 'mvn clean package'
			}
		}
	}
}