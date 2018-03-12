
echo 'Deployemnt in Dev'

stage 'Dev'

node {
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  maven 'clean package'
  //dir('target') {stash name: 'war', includes: '/*.war'}
  checkout scm
  sh 'make'
  stash includes: '**/target/*.jar', name: 'app' 
}
