pipeline{
	agent any
	stages {
		stage ('Build'){
			steps {
				echo 'Running Build now ....'
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar,**/target/*.war', fingerprint: true
			}
		}
		stage ('Test'){
			steps{
				echo 'Running Test now ....'
				junit '**/target/surefire/*.xml'
			}
		}
	}
}
