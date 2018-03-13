
echo 'Deployemnt in Dev'

pipeline {

	agent none
	
    stages {
        stage('Dev1') {
			steps{
				git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
			}
			steps{
				def mvnHome = tool 'M3'
			}
			steps{
				bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
			}
			steps{
				dir('target') {stash name: 'jar', includes: '/*.jar'}
			}
	}
   }
}

