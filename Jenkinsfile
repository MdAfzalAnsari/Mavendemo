
echo 'Deployemnt in Dev'

stage 'Dev'

node {
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  def mvnHome = tool 'M3'
  bat "${mvnHome}\\bin\\mvn -B verify"
  //dir('target') {stash name: 'war', includes: '/*.war'
}
