
echo 'Deployemnt in Dev'

stage 'Dev'

node {
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  mvn 'clean package'
  dir('target') {stash name: 'war', includes: 'x.war'}
}
