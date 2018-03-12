
echo 'Deployemnt in Dev'

pipeline {

	agent any
	
    stages {
        stage('Dev1') {
           git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  		   def mvnHome = tool 'M3'
		   bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
		   dir('target') {stash name: 'jar', includes: '/*.jar'}
        }
	}
}