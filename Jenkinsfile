
echo 'Deployemnt in Dev'

pipeline {

	agent none
	
    stages {
        stage('Cloning') {
			steps{
				git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
			}
	}
	stage('Environment'){
			steps{
				def mvnHome = tool 'M3'
			}
	}
	stage('Building artifact'){
			steps{
				bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
			}
	}
	stage('including artifact'){
		    steps{
				dir('target') {stash name: 'jar', includes: 'target/*.jar'}
			        git add .
				git commit -m "added jar file"
			    	git push -u credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
			}
	}
   }
}

