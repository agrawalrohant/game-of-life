pipeline{
	agent any
	stages {
		stage ('Build'){
			steps {
				echo "Running stage Build for Id ${evn.BUILD_ID} on ${env.JENKINS_URL} now ...."
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar,**/target/*.war', fingerprint: true
			}
		}
		stage ('Test'){
			steps{
				echo 'Running Test now ....'
				junit '**/target/surefire-reports/*.xml'
			}
		}
	}
}
