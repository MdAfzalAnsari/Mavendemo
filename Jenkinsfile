
echo 'Deployemnt in Dev'
node{  

	stage 'Checkout'
		checkout scm
        stage 'Cloning' 		
		git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
	stage 'Environment'
		def mvnHome = tool 'M3'
	stage 'Building artifact'
		bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
	stage 'including artifact'
	   	dir('target') {stash name: 'jar', includes: 'target/*.jar'}			        
	
}

