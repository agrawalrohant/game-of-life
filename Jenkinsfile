pipeline{
	agent any
	stages {
		stage ('Build'){
			steps {
				echo 'build...'
				bat 'make 
				bat mvn clean build
			}
		}
		stage ('Test'){
			steps{
				echo 'test....'
				bat 'make check || true' 
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