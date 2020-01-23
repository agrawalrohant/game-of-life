pipeline{
	agent any
	stages {
		stage ('Build'){
			steps {
				echo "Running Stage Build # ${env.BUILD_ID} on URL ${env.JENKINS_URL}"
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar,**/target/*.war', fingerprint: true
			}
		}
	}
	post {
		always {
			echo "Scanning Test Results for # ${env.BUILD_ID} on URL ${env.JENKINS_URL}"
		    junit '**/target/surefire-reports/*.xml'
		}
		failure {
		    echo 'Oh.. no! The Pipeline failed :('
		}
    }
}
