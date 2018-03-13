echo 'Deployemnt in Dev'
echo 'Running JenkinsFIle'
stage 'Dev'

node {  
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  def mvnHome = tool 'M3'
  bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
  dir('target') {stash name: 'jar', includes: '/*.jar'}
}
