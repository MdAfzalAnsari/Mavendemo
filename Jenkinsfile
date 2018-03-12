
echo 'Deployemnt in Dev'

stage 'Dev'

node {
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  def mvnHome = tool 'M3'
  
  bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
  //dir('target') {stash name: 'war', includes: '/*.war'
}
